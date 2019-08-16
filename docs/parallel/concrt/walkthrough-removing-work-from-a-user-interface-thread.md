---
title: Пошаговое руководство. Удаление работы из потока пользовательского интерфейса
ms.date: 04/25/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 214796777968c8aec7116a848e791aeef0d3af7b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512262"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Пошаговое руководство. Удаление работы из потока пользовательского интерфейса

В этом документе показано, как использовать среда выполнения с параллелизмом для перемещения работы, выполняемой потоком ПОЛЬЗОВАТЕЛЬСКОГО интерфейса в приложении Microsoft Foundation Classes (MFC) в рабочий поток. В этом документе также показано, как повысить производительность длительной операции рисования.

Удаление работы из потока пользовательского интерфейса путем разгрузки операций блокировки, например рисования, в рабочие потоки может повысить скорость реагирования приложения. В этом пошаговом руководстве используется процедура рисования, которая создает фрактал Мандельброта, чтобы продемонстрировать длительную операцию блокировки. Поколение фрактала Мандельброта также является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений.

## <a name="prerequisites"></a>Предварительные требования

Перед началом работы с этим пошаговым руководством ознакомьтесь со следующими разделами:

- [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

- [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)

Мы также рекомендуем ознакомиться с основами разработки приложений MFC и GDI+, прежде чем приступать к этому пошаговому руководству. Дополнительные сведения о MFC см. в статье [классическое приложение MFC](../../mfc/mfc-desktop-applications.md). Дополнительные сведения о GDI+ см. в разделе [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Создание приложения MFC](#application)

- [Реализация серийной версии приложения фрактала Мандельброта](#serial)

- [Удаление работы из потока пользовательского интерфейса](#removing-work)

- [Повышение производительности рисования](#performance)

- [Добавление поддержки отмены](#cancellation)

##  <a name="application"></a>Создание приложения MFC

В этом разделе описывается создание базового приложения MFC.

### <a name="to-create-a-visual-c-mfc-application"></a>Создание приложения Visual C++ MFC

1. Используйте **Мастер приложений MFC** для создания приложения MFC со всеми параметрами по умолчанию. См. [Пошаговое руководство: Использование новых элементов управления](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) оболочки MFC для получения инструкций о том, как открыть мастер для вашей версии Visual Studio.

1. Введите имя проекта, `Mandelbrot`например, и нажмите кнопку **ОК** , чтобы открыть **Мастер приложений MFC**.

1. В области **Тип приложения** выберите **один документ**. Убедитесь, что флажок " **Поддержка архитектуры документов/представлений** " снят.

1. Нажмите кнопку **Готово** , чтобы создать проект и закрыть **Мастер приложений MFC**.

   Убедитесь, что приложение успешно создано путем его сборки и запуска. Чтобы выполнить сборку приложения, в меню **Сборка** выберите пункт **построить решение**. Если приложение успешно строится, запустите его, выбрав команду **начать отладку** в меню **Отладка** .

##  <a name="serial"></a>Реализация серийной версии приложения фрактала Мандельброта

В этом разделе описывается рисование фрактала Мандельброта. Эта версия рисует фрактал Мандельброта в объекте GDI+ [Bitmap](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) , а затем копирует содержимое этого растрового изображения в окно клиента.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Реализация серийной версии приложения фрактала Мандельброта

1. В файле stdafx. h добавьте следующую `#include` директиву:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. В чилдвиев. h после `pragma` директивы `BitmapPtr` определите тип. Тип позволяет использовать указатель `Bitmap` на объект для совместного использования несколькими компонентами. `BitmapPtr` `Bitmap` Объект удаляется, если на него больше не ссылается ни один компонент.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. В чилдвиев. h добавьте следующий код в `protected` раздел `CChildView` класса:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. В Чилдвиев. cpp закомментируйте или удалите следующие строки.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   В отладочных сборках этот шаг не дает приложению использовать `DEBUG_NEW` распределитель, который несовместим с GDI+.

1. В чилдвиев. cpp добавьте `using` директиву `Gdiplus` в пространство имен.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Добавьте следующий код в конструктор и деструктор `CChildView` класса для инициализации и завершения работы GDI+.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Выполните метод `CChildView::DrawMandelbrot`. Этот метод рисует фрактал Мандельброта в указанном `Bitmap` объекте.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Выполните метод `CChildView::OnPaint`. Этот метод вызывает `CChildView::DrawMandelbrot` , а затем копирует содержимое `Bitmap` объекта в окно.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

На следующем рисунке показаны результаты применения приложения фрактала Мандельброта.

![Приложение фрактала Мандельброта](../../parallel/concrt/media/mandelbrot.png "Приложение фрактала Мандельброта")

Поскольку вычисления для каждого пикселя являются ресурсоемкими, поток пользовательского интерфейса не может обрабатывать дополнительные сообщения до тех пор, пока не завершится общее вычисление. Это может снизить скорость реагирования в приложении. Однако эту проблему можно освободить, удалив работу из потока пользовательского интерфейса.

[[В начало](#top)]

##  <a name="removing-work"></a>Удаление работы из потока пользовательского интерфейса

В этом разделе показано, как удалить работу по отрисовке из потока пользовательского интерфейса в приложении фрактала Мандельброта. Перемещая работу по отрисовке из потока пользовательского интерфейса в рабочий поток, поток пользовательского интерфейса может обрабатывать сообщения, когда рабочий поток создает изображение в фоновом режиме.

Среда выполнения с параллелизмом предоставляет три способа выполнения задач: [группы задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md), асинхронные [агенты](../../parallel/concrt/asynchronous-agents.md)и упрощенные [задачи](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Хотя можно использовать любой из этих механизмов для удаления работы из потока пользовательского интерфейса, в этом примере используется объект [Concurrency:: task_group](reference/task-group-class.md) , так как группы задач поддерживают отмену. В этом пошаговом руководстве будет использоваться Отмена, чтобы уменьшить объем работы, выполняемой при изменении размера окна клиента, и выполнить очистку при уничтожении окна.

В этом примере также используется объект [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , позволяющий ПОТОКУ пользовательского интерфейса и рабочему потоку взаимодействовать друг с другом. После того, как рабочий поток создаст образ, он отправляет указатель на `Bitmap` объект `unbounded_buffer` объекту, а затем отправляет сообщение Paint в поток пользовательского интерфейса. Затем поток пользовательского интерфейса получает от `unbounded_buffer` `Bitmap` объекта объект и отображает его в клиентском окне.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Удаление работы по отрисовке из потока пользовательского интерфейса

1. В файле stdafx. h добавьте следующие `#include` директивы:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. В `task_group` чилдвиев. h добавьте переменные члена и `unbounded_buffer` `CChildView` в `protected` раздел класса. Объект содержит задачи, выполняющие рисование `unbounded_buffer` ; объект содержит готовое изображение фрактала Мандельброта. `task_group`

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. В чилдвиев. cpp добавьте `using` директиву `concurrency` в пространство имен.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. В методе после `Bitmap::UnlockBits`вызова вызовите функцию `Bitmap` [Concurrency:: send](reference/concurrency-namespace-functions.md#send) , чтобы передать объект в поток пользовательского интерфейса. `CChildView::DrawMandelbrot` Затем опубликуйте сообщение Paint в потоке пользовательского интерфейса и сделает клиентскую область недействительной.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Обновите `Bitmap` метод, чтобы получить обновленный объект, и нарисуйте изображение в клиентском окне. `CChildView::OnPaint`

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint` Метод создает задачу для создания изображения фрактала Мандельброта, если он не существует в буфере сообщений. Буфер сообщений не будет содержать `Bitmap` объект в таких случаях, как исходное сообщение Paint, и когда другое окно будет перемещено перед окном клиента.

1. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

Теперь пользовательский интерфейс больше отвечает, поскольку работа по отрисовке выполняется в фоновом режиме.

[[В начало](#top)]

##  <a name="performance"></a>Повышение производительности рисования

Поколение фрактала Мандельброта является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений. Для параллелизации процедуры рисования преобразуйте внешний `for` цикл `CChildView::DrawMandelbrot` в методе в вызов алгоритма [Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) , как показано ниже.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Поскольку вычисление каждого элемента Bitmap является независимым, нет необходимости синхронизировать операции рисования, обращающиеся к памяти растрового изображения. Это позволяет масштабировать производительность по мере увеличения количества доступных процессоров.

[[В начало](#top)]

##  <a name="cancellation"></a>Добавление поддержки отмены

В этом разделе описывается, как управлять изменением размера окна и отменять любые активные задачи рисования при уничтожении окна.

Отмена документа [в PPL](cancellation-in-the-ppl.md) объясняет, как работает Отмена в среде выполнения. Отмена осуществляется совместно; Поэтому он не выполняется немедленно. Чтобы отменить отмененную задачу, среда выполнения создает внутреннее исключение во время последующего вызова из задачи в среду выполнения. В предыдущем разделе показано, как использовать `parallel_for` алгоритм для повышения производительности задачи рисования. Вызов метода `parallel_for` позволяет среде выполнения прерывать задачу и, следовательно, позволяет выполнять отмену.

### <a name="cancelling-active-tasks"></a>Отмена активных задач

Приложение фрактала Мандельброта `Bitmap` создает объекты, размеры которых соответствуют размеру клиентского окна. При каждом изменении размера окна клиента приложение создает дополнительную фоновую задачу для создания изображения для нового размера окна. Приложению не требуются эти промежуточные образы; для этого требуется только изображение для конечного размера окна. Чтобы приложение не выполняло эту дополнительную работу, можно отменить все активные задачи рисования в обработчиках сообщений для `WM_SIZE` сообщений и `WM_SIZING` , а затем перепланировать работу рисования после изменения размера окна.

Чтобы отменить активные задачи рисования при изменении размера окна, приложение вызывает метод [Concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) в обработчиках `WM_SIZING` сообщений и `WM_SIZE` . Обработчик для `WM_SIZE` сообщения также вызывает метод [Concurrency:: task_group:: wait](reference/task-group-class.md#wait) для ожидания завершения всех активных задач, а затем повторно планирует задачу рисования для обновленного размера окна.

При удалении клиентского окна рекомендуется отменить все активные задачи рисования. Отмена любых активных задач рисования гарантирует, что рабочие потоки не передают сообщения в поток пользовательского интерфейса после уничтожения окна клиента. Приложение отменяет все активные задачи рисования в обработчике `WM_DESTROY` сообщения.

### <a name="responding-to-cancellation"></a>Реагирование на отмену

`CChildView::DrawMandelbrot` Метод, выполняющий задачу рисования, должен реагировать на отмену. Поскольку среда выполнения использует обработку исключений для отмены задач, `CChildView::DrawMandelbrot` метод должен использовать надежный механизм, гарантирующий правильную очистку всех ресурсов. В этом примере используется шаблон « *получение ресурсов — инициализация* » (RAII), гарантирующий, что при отмене задачи биты растрового изображения разблокируются.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Добавление поддержки отмены в приложение фрактала Мандельброта

1. В чилдвиев. h в `protected` разделе `CChildView` класса добавьте объявления для `OnSize`функций схемы сообщений, `OnSizing`и `OnDestroy` .

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. В чилдвиев. cpp измените схему сообщений, чтобы она `WM_SIZE`содержала обработчики для сообщений, `WM_SIZING`и `WM_DESTROY` .

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Выполните метод `CChildView::OnSizing`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Выполните метод `CChildView::OnSize`. Этот метод отменяет все существующие задачи рисования и создает новую задачу рисования для обновленного размера окна клиента.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Выполните метод `CChildView::OnDestroy`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. В чилдвиев. cpp Определите `scope_guard` класс, реализующий шаблон RAII.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Добавьте следующий код в `CChildView::DrawMandelbrot` метод после `Bitmap::LockBits`вызова:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Этот код обрабатывает отмену, создавая `scope_guard` объект. Когда объект оставляет область, он разблокирует биты точечного рисунка.

1. Измените конец `CChildView::DrawMandelbrot` метода, чтобы `scope_guard` отклонить объект после разблокировки битов растрового изображения, но перед отправкой сообщений в поток пользовательского интерфейса. Это гарантирует, что поток пользовательского интерфейса не будет обновлен до разблокировки битов растрового изображения.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

При изменении размера окна работа по отрисовке выполняется только для конечного размера окна. Любые активные задачи рисования также отменяются при уничтожении окна.

[[В начало](#top)]

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)
