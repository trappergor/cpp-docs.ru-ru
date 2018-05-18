---
title: 'Пошаговое руководство: Удаление задач из потока пользовательского интерфейса | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0502ce728c35b08d927cea48ee5b82756980aec5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Пошаговое руководство. Удаление задач из потоков пользовательского интерфейса
В этом документе показано, как использовать среду выполнения с параллелизмом для перемещения операций, который выполняется потоком пользовательского интерфейса (UI) в приложении Microsoft Foundation Classes (MFC) рабочий поток. В этом документе также показано, как повысить производительность продолжительной операции рисования.  
  
 Удаление работы из потока пользовательского интерфейса путем выгрузки блокирующих операций, например, рисование в рабочий поток может повысить скорость реагирования приложения. В этом пошаговом руководстве используется процедура отрисовки, приводит к возникновению ошибки фрактал "Мандельброт", чтобы продемонстрировать длительной блокирующей операции. Поколение фрактал "Мандельброт" также является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, ознакомьтесь со следующими разделами:  
  
-   [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
-   [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)  
  
 Рекомендуется также, что вы понимаете основные принципы разработки приложений MFC и [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] перед выполнением этого пошагового руководства. Дополнительные сведения о MFC см. в разделе [настольные приложения MFC](../../mfc/mfc-desktop-applications.md). Дополнительные сведения о [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)], в разделе [GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798).  
  
##  <a name="top"></a> Разделы  
 Это пошаговое руководство содержит следующие разделы:  
  
-   [Создание приложения MFC](#application)  
  
-   [Реализации последовательной версии приложение "Мандельброт"](#serial)  
  
-   [Удаление работы из потока пользовательского интерфейса](#removing-work)  
  
-   [Повышение производительности отрисовки](#performance)  
  
-   [Добавление поддержки отмены](#cancellation)  
  
##  <a name="application"></a> Создание приложения MFC  
 В этом разделе описывается создание простого приложения MFC.  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Создание приложения Visual C++ MFC  
  
1.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
2.  В **новый проект** диалогового **установленные шаблоны** выберите **Visual C++**, а затем в **шаблоны** выберите **Приложение MFC**. Введите имя проекта, например `Mandelbrot`, а затем нажмите кнопку **ОК** для отображения **мастер приложений MFC**.  
  
3.  В **тип приложения** выберите **однооконный**. Убедитесь, что **поддержка архитектуры Document/View** флажок снят.  
  
4.  Нажмите кнопку **Готово** создать проект и закрыть **мастер приложений MFC**.  
  
     Убедитесь, что приложение успешно создано, построения и выполнения его. Для сборки приложения, в **построения** меню, нажмите кнопку **построить решение**. Если сборка приложения прошла успешно, запустите приложение, нажав кнопку **начать отладку** на **отладки** меню.  
  
##  <a name="serial"></a> Реализации последовательной версии приложение "Мандельброт"  
 Этот раздел описывает способ рисования фрактал "Мандельброт". Эта версия отрисовывает фрактал "Мандельброт" для [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [растрового изображения](https://msdn.microsoft.com/library/ms534420.aspx) объекта и затем копирует содержимое этого растрового изображения в окне клиента.  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Для реализации последовательных версии приложение "Мандельброт"  
  
1.  Добавьте в файл stdafx.h следующие `#include` директиву:  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  В файле ChildView.h после `pragma` директивы, определить `BitmapPtr` типа. `BitmapPtr` Типа включает указатель на `Bitmap` объект общим для нескольких компонентов. `Bitmap` Объект удаляется, когда он больше не ссылается ни один компонент.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  В файле ChildView.h добавьте следующий код в `protected` раздел `CChildView` класса:  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  В файле ChildView.cpp закомментируйте или удалите следующие строки.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     В отладочных построениях, этот шаг предотвращает использование приложением `DEBUG_NEW` распределителя, который несовместим с [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
5.  В файле ChildView.cpp добавьте `using` директиву `Gdiplus` пространства имен.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  Добавьте следующий код в конструктор и деструктор класса `CChildView` для инициализации и завершения работы [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  Выполните метод `CChildView::DrawMandelbrot`. Этот метод отрисовывает фрактал "Мандельброт" указанного `Bitmap` объекта.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  Выполните метод `CChildView::OnPaint`. Этот метод вызывает метод `CChildView::DrawMandelbrot` и затем копирует содержимое `Bitmap` объект в окно.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. Убедитесь, что приложение было успешно обновлено, построения и запустив его.  
  
 Ниже показаны результаты приложение "Мандельброт".  
  
 ![Приложение "Мандельброт"](../../parallel/concrt/media/mandelbrot.png ""Мандельброт"")  
  
 Поскольку вычисление каждого пикселя требовательных к вычислительным ресурсам, поток пользовательского интерфейса не может обрабатывать дополнительные сообщения до окончания всего вычисления. Это может снизить скорость ответа приложения. Тем не менее вы сможете уменьшить эту проблему путем удаления работы из потока пользовательского интерфейса.  
  
 [[В начало](#top)]  
  
##  <a name="removing-work"></a> Удаление работы из потока пользовательского интерфейса  
 В этом разделе показано, как удалить по отрисовке из потока пользовательского интерфейса в приложение "Мандельброт". Переместив отрисовке из потока пользовательского интерфейса в рабочий поток, поток пользовательского интерфейса может обрабатывать сообщения, как рабочий поток создает изображение в фоновом режиме.  
  
 Среда выполнения с параллелизмом предоставляет три способа запуска задач: [групп задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [асинхронных агентов](../../parallel/concrt/asynchronous-agents.md), и [упрощенных задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Несмотря на то, что один из этих механизмов можно использовать для удаления работы из потока пользовательского интерфейса, в этом примере используется [concurrency::task_group](reference/task-group-class.md) поскольку группы задач поддерживают отмену. В данном пошаговом руководстве, более поздней версии, использующего отмену для сокращения объема работы, выполняемой при изменении размера окна клиента и для выполнения очистки при уничтожении окна.  
  
 В этом примере также используется [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта для участия в потоке пользовательского интерфейса и рабочим потоком для взаимодействия друг с другом. После того, как рабочий поток сгенерировал изображение, он отправляет указатель `Bitmap` объект `unbounded_buffer` объекта и затем отправляет сообщение изображения в поток пользовательского интерфейса. Поток пользовательского интерфейса, затем получает от `unbounded_buffer` объекта `Bitmap` объекта и отображает его в окне клиента.  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Для удаления по отрисовке из потока пользовательского интерфейса  
  
1.  Добавьте в файл stdafx.h следующие `#include` директивы:  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  В файле ChildView.h добавьте `task_group` и `unbounded_buffer` переменных-членов в `protected` раздел `CChildView` класса. `task_group` Объект содержит задачи, выполняющие отрисовку; `unbounded_buffer` объект содержит завершенного образа "Мандельброт".  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  В файле ChildView.cpp добавьте `using` директиву `concurrency` пространства имен.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  В `CChildView::DrawMandelbrot` метод после вызова `Bitmap::UnlockBits`, вызовите [concurrency::send](reference/concurrency-namespace-functions.md#send) функции для передачи `Bitmap` объекта в поток пользовательского интерфейса. Затем отправьте сообщение изображения в поток пользовательского интерфейса и удалите клиентскую область.  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  Обновление `CChildView::OnPaint` метод для получения обновленного `Bitmap` объекта и отобразите изображение в окне клиента.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` Метод создает задачу по созданию изображения "Мандельброт", если она отсутствует в буфере сообщений. Буфер сообщений не содержит `Bitmap` объекта в случае, например начальной отправку сообщения, или другое окно перемещается поверх окна клиента.  
  
6.  Убедитесь, что приложение было успешно обновлено, построения и запустив его.  
  
 Пользовательский Интерфейс теперь отклика, поскольку рисования работа выполняется в фоновом режиме.  
  
 [[В начало](#top)]  
  
##  <a name="performance"></a> Повышение производительности отрисовки  

 Создание фрактал "Мандельброт" является хорошим кандидатом для параллелизации, поскольку вычисление каждого пикселя не зависит от других вычислений. Для параллелизации процесса отрисовки, преобразуйте внешний `for` цикл в `CChildView::DrawMandelbrot` метод вызова [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритма, как показано ниже.  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 Поскольку вычисление каждого элемента растрового изображения не зависит, не требуется синхронизировать операции рисования, доступ к памяти растрового изображения. Это улучшает производительность пропорционально как число доступных процессоров увеличивается.  
  
 [[В начало](#top)]  
  
##  <a name="cancellation"></a> Добавление поддержки отмены  
 В этом разделе описывается, как обрабатывать изменения размера окна и Отмена все активных задач рисования при уничтожении окна.  
  
 Документ [Отмена в PPL](cancellation-in-the-ppl.md) объясняет, как работает Отмена в среде выполнения. Отмена выполняется совместно; Таким образом он не происходит немедленно. Чтобы остановить отмененной задачи, среда выполнения создает исключение в ходе последующего вызова из задачи во время выполнения. В предыдущем разделе показано, как использовать `parallel_for` алгоритм для повышения производительности задачу отрисовки. Вызов `parallel_for` позволяет среде выполнения для отмены задачи и поэтому обеспечивает возможность отмены для работы.  
  
### <a name="cancelling-active-tasks"></a>Отмена активных задач  
 Приложение "Мандельброт" создает `Bitmap` объекты, размеры которого совпадает с размером в окне клиента. Каждый раз при изменении размера окна клиента, приложение создает фоновую задачу для создания изображения для нового размера окна. Приложения не требуются промежуточные изображения; Это требует только образ для конечного размера окна. Чтобы запретить выполнение дополнительной работы приложения, можно отменить любые активных задач рисования в обработчике сообщений для `WM_SIZE` и `WM_SIZING` сообщения и затем перепланировать Рисование работать после изменения размеров окна.  
  
 Для отмены активных задач рисования при изменении размера окна, приложение вызывает [Concurrency::task_group:: Cancel](reference/task-group-class.md#cancel) метод в обработчиках для `WM_SIZING` и `WM_SIZE` сообщений. Обработчик `WM_SIZE` сообщений также вызовы [Concurrency::task_group:: wait](reference/task-group-class.md#wait) метод для ожидания для всех активных задач для завершения, а затем планирует новую задачу отрисовки для обновленного размера окна.  
  
 При уничтожении окна клиента, рекомендуется отменить любые активных задач рисования. Отмена любой активных задач рисования гарантирует, что рабочие потоки не будет отсылать сообщения в поток пользовательского интерфейса после уничтожения окна клиента. Приложение отменяет любые активных задач рисования в обработчике `WM_DESTROY` сообщения.  
  
### <a name="responding-to-cancellation"></a>Реакция на отмену  
 `CChildView::DrawMandelbrot` Метод, который выполняет задачу отрисовки, должны реагировать на отмену. Поскольку среда выполнения использует обработку исключений для отмены задачи, `CChildView::DrawMandelbrot` метод должен использовать механизм исключений, чтобы гарантировать правильность очистку всех ресурсов. В этом примере используется *Получение ресурса есть инициализация* шаблон (RAII), чтобы гарантировать, что после отмены задачи биты растрового изображения будут разблокированы.  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Добавление поддержки отмены в приложение "Мандельброт"  
  
1.  В файле ChildView.h в `protected` раздел `CChildView` добавьте объявления для `OnSize`, `OnSizing`, и `OnDestroy` функции схемы сообщений.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  В файле ChildView.cpp измените схему сообщения, чтобы она содержала обработчики `WM_SIZE`, `WM_SIZING`, и `WM_DESTROY` сообщений.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  Выполните метод `CChildView::OnSizing`. Этот метод отменяет любые существующие задачи рисования.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  Выполните метод `CChildView::OnSize`. Этот метод отменяет любые существующие задачи рисования и создает новую задачу отрисовки для размера окна обновленный клиент.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  Выполните метод `CChildView::OnDestroy`. Этот метод отменяет любые существующие задачи рисования.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  В файле ChildView.cpp определить `scope_guard` класс, который реализует шаблон RAII.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  Добавьте следующий код в `CChildView::DrawMandelbrot` метод после вызова `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     Этот код обрабатывает отмену, создав `scope_guard` объекта. Когда объект покидает область, он разблокирует биты растрового изображения.  
  
8.  Измените окончание `CChildView::DrawMandelbrot` метод, чтобы закрыть `scope_guard` объекта после биты растрового изображения разблокированы, но перед отправкой сообщения в поток пользовательского интерфейса. Это гарантирует, что поток пользовательского интерфейса не обновляется до биты растрового изображения разблокированы.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. Убедитесь, что приложение было успешно обновлено, построения и запустив его.  
  
 При изменении размера окна, вычисления по отрисовке выполняются только для окончательного размера окна. Любой активных задач рисования отменяется при уничтожении окна.  
  
 [[В начало](#top)]  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)
