---
title: Пошаговое руководство. Удаление задач из потоков пользовательского интерфейса
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 518044d4e3adea44c3776793c8277939076066d6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140711"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Пошаговое руководство. Удаление задач из потоков пользовательского интерфейса

В этом документе показано, как использовать среда выполнения с параллелизмом для перемещения работы, выполняемой потоком ПОЛЬЗОВАТЕЛЬСКОГО интерфейса в приложении Microsoft Foundation Classes (MFC) в рабочий поток. В этом документе также показано, как повысить производительность длительной операции рисования.

Удаление работы из потока пользовательского интерфейса путем разгрузки операций блокировки, например рисования, в рабочие потоки может повысить скорость реагирования приложения. В этом пошаговом руководстве используется процедура рисования, которая создает фрактал Мандельброта, чтобы продемонстрировать длительную операцию блокировки. Поколение фрактала Мандельброта также является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений.

## <a name="prerequisites"></a>предварительные требования

Перед началом работы с этим пошаговым руководством ознакомьтесь со следующими разделами:

- [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

- [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)

Мы также рекомендуем ознакомиться с основами разработки приложений MFC и GDI+, прежде чем приступать к этому пошаговому руководству. Дополнительные сведения о MFC см. в статье [классическое приложение MFC](../../mfc/mfc-desktop-applications.md). Дополнительные сведения о GDI+ см. в разделе [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

## <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Создание приложения MFC](#application)

- [Реализация серийной версии приложения фрактала Мандельброта](#serial)

- [Удаление работы из потока пользовательского интерфейса](#removing-work)

- [Повышение производительности рисования](#performance)

- [Добавление поддержки отмены](#cancellation)

## <a name="application"></a>Создание приложения MFC

В этом разделе описывается создание базового приложения MFC.

### <a name="to-create-a-visual-c-mfc-application"></a>Создание приложения Visual C++ MFC

1. Используйте **Мастер приложений MFC** для создания приложения MFC со всеми параметрами по умолчанию. Инструкции по открытию мастера для вашей версии Visual Studio см. в разделе [Пошаговое руководство. Использование новых элементов управления оболочки MFC](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) .

1. Введите имя проекта, например `Mandelbrot`, а затем нажмите кнопку **ОК** , чтобы открыть **Мастер приложений MFC**.

1. В области **Тип приложения** выберите **один документ**. Убедитесь, что флажок " **Поддержка архитектуры документов/представлений** " снят.

1. Нажмите кнопку **Готово** , чтобы создать проект и закрыть **Мастер приложений MFC**.

   Убедитесь, что приложение успешно создано путем его сборки и запуска. Чтобы выполнить сборку приложения, в меню **Сборка** выберите пункт **построить решение**. Если приложение успешно строится, запустите его, выбрав команду **начать отладку** в меню **Отладка** .

## <a name="serial"></a>Реализация серийной версии приложения фрактала Мандельброта

В этом разделе описывается рисование фрактала Мандельброта. Эта версия рисует фрактал Мандельброта в объекте GDI+ [Bitmap](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) , а затем копирует содержимое этого растрового изображения в окно клиента.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Реализация серийной версии приложения фрактала Мандельброта

1. В файле *PCH. h* (*stdafx. h* в Visual Studio 2017 и более ранних версиях) добавьте следующую директиву `#include`:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. В Чилдвиев. h после директивы `pragma` определите тип `BitmapPtr`. Тип `BitmapPtr` позволяет использовать указатель на объект `Bitmap` для совместного использования несколькими компонентами. Объект `Bitmap` удаляется, если на него больше не ссылается ни один компонент.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. В Чилдвиев. h добавьте следующий код в раздел `protected` класса `CChildView`:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. В Чилдвиев. cpp закомментируйте или удалите следующие строки.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   В отладочных сборках этот шаг не дает приложению использовать распределитель `DEBUG_NEW`, который несовместим с GDI+.

1. В Чилдвиев. cpp добавьте директиву `using` в пространство имен `Gdiplus`.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Добавьте следующий код в конструктор и деструктор класса `CChildView` для инициализации и завершения работы GDI+.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Выполните метод `CChildView::DrawMandelbrot`. Этот метод выводит фрактал Мандельброта в указанный объект `Bitmap`.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Выполните метод `CChildView::OnPaint`. Этот метод вызывает `CChildView::DrawMandelbrot`, а затем копирует содержимое объекта `Bitmap` в окно.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

На следующем рисунке показаны результаты применения приложения фрактала Мандельброта.

![Приложение фрактала Мандельброта](../../parallel/concrt/media/mandelbrot.png "Приложение "Мандельброт"")

Поскольку вычисления для каждого пикселя являются ресурсоемкими, поток пользовательского интерфейса не может обрабатывать дополнительные сообщения до тех пор, пока не завершится общее вычисление. Это может снизить скорость реагирования в приложении. Однако эту проблему можно освободить, удалив работу из потока пользовательского интерфейса.

[[В начало](#top)]

## <a name="removing-work"></a>Удаление работы из потока пользовательского интерфейса

В этом разделе показано, как удалить работу по отрисовке из потока пользовательского интерфейса в приложении фрактала Мандельброта. Перемещая работу по отрисовке из потока пользовательского интерфейса в рабочий поток, поток пользовательского интерфейса может обрабатывать сообщения, когда рабочий поток создает изображение в фоновом режиме.

Среда выполнения с параллелизмом предоставляет три способа выполнения задач: [группы задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)и [упрощенные задачи](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Хотя можно использовать любой из этих механизмов для удаления работы из потока пользовательского интерфейса, в этом примере используется объект [Concurrency:: task_group](reference/task-group-class.md) , так как группы задач поддерживают отмену. В этом пошаговом руководстве будет использоваться Отмена, чтобы уменьшить объем работы, выполняемой при изменении размера окна клиента, и выполнить очистку при уничтожении окна.

В этом примере также используется объект [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , позволяющий ПОТОКУ пользовательского интерфейса и рабочему потоку взаимодействовать друг с другом. После того как рабочий поток создаст образ, он отправляет указатель на объект `Bitmap` в объект `unbounded_buffer`, а затем отправляет сообщение Paint в поток пользовательского интерфейса. Затем поток пользовательского интерфейса получает от объекта `unbounded_buffer` объект `Bitmap` и отображает его в клиентском окне.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Удаление работы по отрисовке из потока пользовательского интерфейса

1. В файле *PCH. h* (*stdafx. h* в Visual Studio 2017 и более ранних версиях) добавьте следующие директивы `#include`:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. В Чилдвиев. h добавьте переменные члена `task_group` и `unbounded_buffer` в раздел `protected` класса `CChildView`. Объект `task_group` содержит задачи, выполняющие рисование; Объект `unbounded_buffer` содержит готовое изображение фрактала Мандельброта.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. В Чилдвиев. cpp добавьте директиву `using` в пространство имен `concurrency`.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. В методе `CChildView::DrawMandelbrot` после вызова `Bitmap::UnlockBits`вызовите функцию [Concurrency:: send](reference/concurrency-namespace-functions.md#send) , чтобы передать объект `Bitmap` в поток пользовательского интерфейса. Затем опубликуйте сообщение Paint в потоке пользовательского интерфейса и сделает клиентскую область недействительной.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Обновите метод `CChildView::OnPaint`, чтобы получить обновленный объект `Bitmap`, и нарисуйте изображение в окне клиента.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   Метод `CChildView::OnPaint` создает задачу для создания изображения фрактала Мандельброта, если он не существует в буфере сообщений. Буфер сообщений не будет содержать объект `Bitmap` в таких случаях, как начальное сообщение Paint, и когда другое окно будет перемещено перед окном клиента.

1. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

Теперь пользовательский интерфейс больше отвечает, поскольку работа по отрисовке выполняется в фоновом режиме.

[[В начало](#top)]

## <a name="performance"></a>Повышение производительности рисования

Поколение фрактала Мандельброта является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений. Для параллелизации процедуры рисования преобразуйте внешний цикл `for` в методе `CChildView::DrawMandelbrot` в вызов алгоритма [Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) , как показано ниже.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Поскольку вычисление каждого элемента Bitmap является независимым, нет необходимости синхронизировать операции рисования, обращающиеся к памяти растрового изображения. Это позволяет масштабировать производительность по мере увеличения количества доступных процессоров.

[[В начало](#top)]

## <a name="cancellation"></a>Добавление поддержки отмены

В этом разделе описывается, как управлять изменением размера окна и отменять любые активные задачи рисования при уничтожении окна.

Отмена документа [в PPL](cancellation-in-the-ppl.md) объясняет, как работает Отмена в среде выполнения. Отмена осуществляется совместно; Поэтому он не выполняется немедленно. Чтобы отменить отмененную задачу, среда выполнения создает внутреннее исключение во время последующего вызова из задачи в среду выполнения. В предыдущем разделе показано, как использовать алгоритм `parallel_for` для повышения производительности задачи рисования. Вызов `parallel_for` позволяет среде выполнения прерывать задачу и, следовательно, позволяет выполнять отмену.

### <a name="cancelling-active-tasks"></a>Отмена активных задач

Приложение фрактала Мандельброта создает `Bitmap` объекты, измерения которых соответствуют размеру клиентского окна. При каждом изменении размера окна клиента приложение создает дополнительную фоновую задачу для создания изображения для нового размера окна. Приложению не требуются эти промежуточные образы; для этого требуется только изображение для конечного размера окна. Чтобы приложение не выполняло эту дополнительную работу, можно отменить все активные задачи рисования в обработчиках сообщений для `WM_SIZE` и `WM_SIZING` сообщений, а затем перепланировать работу рисования после изменения размера окна.

Чтобы отменить активные задачи рисования при изменении размера окна, приложение вызывает метод [Concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) в обработчиках для `WM_SIZING` и `WM_SIZE` сообщений. Обработчик для `WM_SIZE` сообщения также вызывает метод [Concurrency:: task_group:: wait](reference/task-group-class.md#wait) для ожидания завершения всех активных задач, а затем повторно планирует задачу рисования для обновленного размера окна.

При удалении клиентского окна рекомендуется отменить все активные задачи рисования. Отмена любых активных задач рисования гарантирует, что рабочие потоки не передают сообщения в поток пользовательского интерфейса после уничтожения окна клиента. Приложение отменяет все активные задачи рисования в обработчике для сообщения `WM_DESTROY`.

### <a name="responding-to-cancellation"></a>Реагирование на отмену

Метод `CChildView::DrawMandelbrot`, выполняющий задачу рисования, должен реагировать на отмену. Поскольку среда выполнения использует обработку исключений для отмены задач, метод `CChildView::DrawMandelbrot` должен использовать надежный механизм, гарантирующий, что все ресурсы будут правильно очищены. В этом примере используется шаблон « *получение ресурсов — инициализация* » (RAII), гарантирующий, что при отмене задачи биты растрового изображения разблокируются.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Добавление поддержки отмены в приложение фрактала Мандельброта

1. В Чилдвиев. h в разделе `protected` класса `CChildView` добавьте объявления для функций `OnSize`, `OnSizing`и `OnDestroy` схемы сообщений.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. В Чилдвиев. cpp измените схему сообщений, чтобы она содержала обработчики для `WM_SIZE`, `WM_SIZING`и `WM_DESTROY` сообщений.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Выполните метод `CChildView::OnSizing`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Выполните метод `CChildView::OnSize`. Этот метод отменяет все существующие задачи рисования и создает новую задачу рисования для обновленного размера окна клиента.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Выполните метод `CChildView::OnDestroy`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. В Чилдвиев. cpp определите класс `scope_guard`, который реализует шаблон RAII.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Добавьте следующий код в метод `CChildView::DrawMandelbrot` после вызова `Bitmap::LockBits`:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Этот код обрабатывает отмену, создавая объект `scope_guard`. Когда объект оставляет область, он разблокирует биты точечного рисунка.

1. Измените конец метода `CChildView::DrawMandelbrot`, чтобы отклонить `scope_guard` объект после разблокировки битов битовой карты, но перед отправкой сообщений в поток пользовательского интерфейса. Это гарантирует, что поток пользовательского интерфейса не будет обновлен до разблокировки битов растрового изображения.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Убедитесь, что приложение успешно Обновлено, создав и запустив его.

При изменении размера окна работа по отрисовке выполняется только для конечного размера окна. Любые активные задачи рисования также отменяются при уничтожении окна.

[[В начало](#top)]

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)
