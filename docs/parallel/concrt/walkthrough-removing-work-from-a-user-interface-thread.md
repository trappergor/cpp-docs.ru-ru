---
title: Пошаговое руководство. Удаление задач из потока пользовательского интерфейса
ms.date: 11/19/2018
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 1838ad0d6adb146adacb8b3a395f44f76e2a8d3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407812"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Пошаговое руководство. Удаление задач из потока пользовательского интерфейса

В этом документе показано, как с помощью среды выполнения с параллелизмом перемещать работу, выполняемую потоком пользовательского интерфейса (UI) в приложении Microsoft Foundation Classes (MFC) в рабочий поток. В этом документе также показано, как повысить производительность продолжительной операции рисования.

Удаление задач из потока пользовательского интерфейса путем выгрузки блокирующих операций, например, рисунок, рабочих потоков может повысить скорость реагирования приложения. В этом пошаговом руководстве используется процедура отрисовки, создающий фрактал Мандельброта для демонстрации длительной операции блокировки. Создание фрактал Мандельброта также является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к этому руководству, ознакомьтесь со следующими разделами:

- [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

- [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)

Также рекомендуется разобраться в основах разработки приложений MFC и GDI +, прежде чем приступать к этому руководству. Дополнительные сведения о MFC см. в разделе [настольные приложения MFC](../../mfc/mfc-desktop-applications.md). Дополнительные сведения о GDI +, см. в разделе [GDI +](https://msdn.microsoft.com/library/windows/desktop/ms533798).

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Создание приложения MFC](#application)

- [Реализация последовательной версии приложение "Мандельброт"](#serial)

- [Удаление задач из потока пользовательского интерфейса](#removing-work)

- [Повышение производительности отрисовки](#performance)

- [Добавление поддержки отмены](#cancellation)

##  <a name="application"></a> Создание приложения MFC

В этом разделе описывается, как создать простое приложение MFC.

### <a name="to-create-a-visual-c-mfc-application"></a>Для создания приложения Visual C++ MFC

1. В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.

1. В **новый проект** отображаемое в диалоговом окне **установленные шаблоны** области выберите **Visual C++**, а затем в **шаблоны** области выберите **Приложения MFC**. Например, введите имя проекта, `Mandelbrot`, а затем нажмите кнопку **ОК** для отображения **мастер приложений MFC**.

1. В **тип приложения** области выберите **одного документа**. Убедитесь, что **поддержка архитектуры Document/View** флажок установлен.

1. Нажмите кнопку **Готово** для создания проекта и закройте **мастер приложений MFC**.

   Убедитесь, что приложение успешно создан путем создания и выполнения его. Для построения приложения, на **построения** меню, щелкните **построить решение**. Если сборка приложения прошла успешно, запустите приложение, выбрав **начать отладку** на **Отладка** меню.

##  <a name="serial"></a> Реализация последовательной версии приложение "Мандельброт"

В этом разделе описывается, как для рисования фрактал Мандельброта. Эта версия отрисовывает фрактал Мандельброта GDI + [точечного рисунка](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) объекта и затем копирует содержимое этого точечного рисунка в окне клиента.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Для реализации последовательной версии приложение "Мандельброт"

1. В файле stdafx.h добавьте следующий `#include` директивы:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. В файле ChildView.h после `pragma` директивы, определить `BitmapPtr` типа. `BitmapPtr` Типа включает указатель на `Bitmap` объект для совместного использования нескольких компонентов. `Bitmap` Объекты удаляются, когда он больше не ссылается ни один компонент.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. В файле ChildView.h добавьте следующий код, чтобы `protected` раздел `CChildView` класса:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. В файле ChildView.cpp закомментируйте или удалите следующие строки.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   В отладочных сборках, этот шаг не позволяет приложению использовать `DEBUG_NEW` распределителя, которая несовместима с использованием GDI +.

1. Добавьте в ChildView.cpp `using` директиву `Gdiplus` пространства имен.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Добавьте следующий код в конструктор и деструктор класса `CChildView` класса для инициализации и завершения работы GDI +.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Выполните метод `CChildView::DrawMandelbrot`. Этот метод рисует фрактал Мандельброта в указанный `Bitmap` объекта.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Выполните метод `CChildView::OnPaint`. Этот метод вызывает метод `CChildView::DrawMandelbrot` и затем копирует содержимое объекта `Bitmap` объект в окно.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Убедитесь, что приложение было успешно обновлено путем создания и выполнения его.

На следующем рисунке результаты приложение "Мандельброт".

![Приложение "Мандельброт"](../../parallel/concrt/media/mandelbrot.png "приложение \"Мандельброт\"")

Потому что вычисления для каждого пикселя требует больших затрат, в потоке пользовательского интерфейса не удается обработать дополнительные сообщения, пока не завершится общее вычисление. Это может снизить скорость ответа приложения. Тем не менее вы сможете уменьшить эту проблему путем удаления работы из потока пользовательского интерфейса.

[[В начало](#top)]

##  <a name="removing-work"></a> Удаление задач из потока пользовательского интерфейса

В этом разделе показано, как удалить по отрисовке из потока пользовательского интерфейса в приложение "Мандельброт". Переместив отрисовке из потока пользовательского интерфейса в рабочий поток, в потоке пользовательского интерфейса может обрабатывать сообщения, как рабочий поток создает изображение в фоновом режиме.

Среда выполнения с параллелизмом предоставляет три способа выполнения задачи: [группы задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [асинхронных агентов](../../parallel/concrt/asynchronous-agents.md), и [упрощенных задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Несмотря на то, что любой из этих механизмов можно использовать для удаления работы из потока пользовательского интерфейса, в этом примере используется [concurrency::task_group](reference/task-group-class.md) объекта, поскольку группы задач поддерживают отмену. В этом пошаговом руководстве, позже, использующего отмену для уменьшения объема работы, которая выполняется при изменении размера окна клиента и для выполнения очистки при уничтожении окна.

В этом примере также используется [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объект для включения в потоке пользовательского интерфейса и рабочего потока для взаимодействия друг с другом. После рабочий поток создает образ, он отправляет указатель на `Bitmap` объект `unbounded_buffer` объекта и затем отправляет сообщение изображения в поток пользовательского интерфейса. В потоке пользовательского интерфейса, затем поступает из `unbounded_buffer` объект `Bitmap` и отрисовывает его в клиентском окне.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Чтобы удалить по отрисовке из потока пользовательского интерфейса

1. В файле stdafx.h добавьте следующий `#include` директивы:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. Добавьте в ChildView.h `task_group` и `unbounded_buffer` переменные-члены `protected` раздел `CChildView` класса. `task_group` Объект содержит задачи, выполняющие отрисовку; `unbounded_buffer` объект содержит завершенного образа Мандельброта.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. Добавьте в ChildView.cpp `using` директиву `concurrency` пространства имен.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. В `CChildView::DrawMandelbrot` метод после вызова `Bitmap::UnlockBits`, вызовите [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию для передачи `Bitmap` объекта в поток пользовательского интерфейса. Затем отправьте сообщение изображения в поток пользовательского интерфейса и удалите клиентскую область.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Обновление `CChildView::OnPaint` метод для получения обновленного `Bitmap` объекта и отобразите изображение в клиентском окне.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint` Метод создает задачу, чтобы создать образ Мандельброта, если она отсутствует в буфере сообщений. Буфер сообщений не будет содержать `Bitmap` объекта в случаях, таких как сообщения начальной рисования, и при перемещении еще одно окно поверх окна клиента.

1. Убедитесь, что приложение было успешно обновлено путем создания и выполнения его.

Пользовательский Интерфейс теперь еще удобнее, так как рисования работа выполняется в фоновом режиме.

[[В начало](#top)]

##  <a name="performance"></a> Повышение производительности отрисовки

Создание фрактал Мандельброта является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений. Для параллелизации процесса отрисовки, преобразуйте внешний `for` цикл `CChildView::DrawMandelbrot` метод для вызова [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритма, как показано ниже.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Так как вычисление каждого элемента растрового изображения не зависит, у вас нет для синхронизации операций рисования, которые обращаются к памяти растрового изображения. Это улучшает производительность, масштабируемость по мере число доступных процессоров увеличивается.

[[В начало](#top)]

##  <a name="cancellation"></a> Добавление поддержки отмены

В этом разделе описывается, как обрабатывать изменения размера окна и способы отмены любой активных задач рисования при уничтожении окна.

Документ [Отмена в PPL](cancellation-in-the-ppl.md) объясняет, как работает Отмена в среде выполнения. Отмена выполняется совместно; Таким образом он не происходит немедленно. Чтобы остановить отмененной задачи, среда выполнения создает внутреннее исключение во время последующего вызова из задачи в среду выполнения. В предыдущем разделе показано, как использовать `parallel_for` алгоритм для повышения производительности задачи по отрисовке изображения. Вызов `parallel_for` позволяет среде выполнения для отмены задачи и таким образом позволяет отмены работы.

### <a name="cancelling-active-tasks"></a>Отмена активных задач

Создает приложение "Мандельброт" `Bitmap` объектов, измерения которой совпадает с размером окна клиента. Каждый раз при изменении размера окна клиента, приложение создает фоновую задачу для создания изображения для нового размера окна. Приложение не требует промежуточные изображения; Это требует только образ для конечного размера окна. Чтобы предотвратить выполнение дополнительной работы приложения, можно отменить любые активные рисования задачи в обработчике сообщений для `WM_SIZE` и `WM_SIZING` сообщения, а затем нарисуйте Перепланирование работать после изменения размеров окна.

Для отмены активных задач рисования при изменении размера окна приложение вызывает [Concurrency::task_group:: Cancel](reference/task-group-class.md#cancel) метода в обработчиках для `WM_SIZING` и `WM_SIZE` сообщений. Обработчик `WM_SIZE` сообщений также вызовы [Concurrency::task_group:: wait](reference/task-group-class.md#wait) метод ожидания для всех активных задач для завершения, а затем планирует новую задачу отрисовки для обновленного размера окна.

При уничтожении окна клиента, рекомендуется отменить любые активных задач рисования. Отмена любой активных задач рисования гарантирует, что рабочих потоков не отправлять сообщения в поток пользовательского интерфейса после уничтожения окна клиента. Приложение отменяет любые активные задачи по отрисовке в обработчике `WM_DESTROY` сообщения.

### <a name="responding-to-cancellation"></a>Отвечать на запросы на отмену

`CChildView::DrawMandelbrot` Метод, который выполняет задачу отрисовки, должны реагировать на отмену. Так как среда выполнения использует обработку исключений для отмены задачи, `CChildView::DrawMandelbrot` метод должен использовать механизм исключений, чтобы обеспечить корректную очистку всех ресурсов. В этом примере используется *Получение ресурса есть инициализация* шаблон (RAII), чтобы гарантировать, что биты растрового изображения разблокированы, когда задача была отменена.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Чтобы добавить поддержку отмены в приложение "Мандельброт"

1. В файле ChildView.h в `protected` раздел `CChildView` добавьте объявления для `OnSize`, `OnSizing`, и `OnDestroy` сообщений функции карты.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. В файле ChildView.cpp измените схему сообщения должен содержать обработчики для `WM_SIZE`, `WM_SIZING`, и `WM_DESTROY` сообщений.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Выполните метод `CChildView::OnSizing`. Этот метод отменяет любые существующие задачи по отрисовке.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Выполните метод `CChildView::OnSize`. Этот метод отменяет любые существующие задачи по отрисовке и создает новую задачу рисования для размера окна обновленного клиента.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Выполните метод `CChildView::OnDestroy`. Этот метод отменяет любые существующие задачи по отрисовке.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. В файле ChildView.cpp определить `scope_guard` класс, который реализует шаблон RAII.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Добавьте следующий код, чтобы `CChildView::DrawMandelbrot` метод после вызова `Bitmap::LockBits`:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Этот код обрабатывает отмену, создав `scope_guard` объекта. Когда объект выходит из области, он разблокирует биты растрового изображения.

1. Изменения в конец `CChildView::DrawMandelbrot` метод, чтобы закрыть `scope_guard` объекта после разблокированы биты растрового изображения, но перед отправкой сообщения в поток пользовательского интерфейса. Это гарантирует, что в потоке пользовательского интерфейса не обновляется до разблокированы биты растрового изображения.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Убедитесь, что приложение было успешно обновлено путем создания и выполнения его.

При изменении размера окна, отрисовке выполняется только для конечного размера окна. Любой активных задач рисования отменяется при уничтожении окна.

[[В начало](#top)]

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)
