---
title: Пошаговое руководство. Удаление задач из потоков пользовательского интерфейса
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 52bc98ef339a19c6ec2a53697f532a9a94b6c9a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377444"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Пошаговое руководство. Удаление задач из потоков пользовательского интерфейса

В этом документе показано, как использовать Время сопряжения runtime для перемещения работы, выполняемой потоком пользовательского интерфейса (UI) в приложении Microsoft Foundation Classes (MFC) в рабочий поток. В этом документе также показано, как повысить производительность длительной операции рисования.

Удаление работы из потока uI путем разгрузки блокирующих операций, например, рисования, в рабочие потоки может улучшить отзывчивость приложения. В этом пошаговом пошаговом действии используется процедура рисования, которая генерирует фрактал Мандельброта, чтобы продемонстрировать длительную операцию блокировки. Поколение фрактала Mandelbrot также является хорошим кандидатом для параллелизации, потому что вычисление каждого пикселя не зависит от всех других вычислений.

## <a name="prerequisites"></a>Предварительные требования

Прочитайте следующие темы, прежде чем начать это пошаговое решение:

- [Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

- [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)

Мы также рекомендуем вам понять основы разработки приложений MFC и GDI, прежде чем начать это пошаговое решение. Для получения дополнительной информации о МФЦ, см [MFC настольных приложений](../../mfc/mfc-desktop-applications.md). Для получения более подробной [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start)информации о GDI, см.

## <a name="sections"></a><a name="top"></a>Разделы

Это пошаговое руководство содержит следующие разделы:

- [Создание приложения MFC](#application)

- [Реализация серийной версии приложения Mandelbrot](#serial)

- [Удаление работы из потока пользователя-интерфейса](#removing-work)

- [Улучшение производительности рисования](#performance)

- [Добавление поддержки отмены](#cancellation)

## <a name="creating-the-mfc-application"></a><a name="application"></a>Создание приложения MFC

В этом разделе описывается, как создать базовое приложение MFC.

### <a name="to-create-a-visual-c-mfc-application"></a>Для создания приложения Visual C е MFC

1. Используйте **приложение MFC Wizard** для создания приложения MFC со всеми настройками по умолчанию. Смотрите [Walkthrough: Использование нового MFC Shell Controls](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) для получения инструкций о том, как открыть мастера для вашей версии Visual Studio.

1. Например, введите имя `Mandelbrot`для проекта, а затем нажмите **OK** для отображения **Мастера приложения MFC.**

1. В панели **типа приложения** выберите **единый документ**. Убедитесь, что флажок **поддержки архитектуры документа/просмотра** будет очищен.

1. Нажмите **Закончить,** чтобы создать проект и закрыть **MFC приложение мастера**.

   Убедитесь, что приложение было успешно создано путем его создания и запуска. Чтобы построить приложение, в меню **сборки,** нажмите **Разрешение сборки**. Если приложение успешно построено, запустите приложение, нажав кнопку **Start Debugging** в меню **Debug.**

## <a name="implementing-the-serial-version-of-the-mandelbrot-application"></a><a name="serial"></a>Реализация серийной версии приложения Mandelbrot

В этом разделе описывается, как нарисовать фрактал Мандельброта. Эта версия притягивает фракталь Mandelbrot к объекту [GDI,](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) а затем копирует содержимое этой битной карты в клиентское окно.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Реализация серийной версии приложения Mandelbrot

1. В *pch.h* *(stdafx.h* в Visual Studio 2017 `#include` и ранее), добавьте следующую директиву:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. В ChildView.h после `pragma` директивы `BitmapPtr` определяют тип. Тип `BitmapPtr` позволяет указателю объекту, `Bitmap` который должен быть общим для нескольких компонентов. Объект `Bitmap` удаляется, когда на него больше не ссылается какой-либо компонент.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. В ChildView.h добавьте следующий `protected` код `CChildView` в раздел класса:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. В ChildView.cpp прокомментируйте или удалите следующие строки.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   В сборках Debug этот шаг предотвращает использование `DEBUG_NEW` приложения аллокатором, который несовместим с GDI.

1. В ChildView.cpp добавьте директиву `using` в `Gdiplus` пространство имен.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Добавьте следующий код к конструктору и `CChildView` деструктору класса, чтобы инициализировать и выключить GDI.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Выполните метод `CChildView::DrawMandelbrot`. Этот метод притягивает фрактал Мандельброта к указанному `Bitmap` объекту.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Выполните метод `CChildView::OnPaint`. Этот метод `CChildView::DrawMandelbrot` вызывает, а затем `Bitmap` копирует содержимое объекта в окно.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Убедитесь, что приложение было успешно обновлено путем его создания и запуска.

Ниже приведены результаты применения Mandelbrot.

![Приложение "Мандельброт"](../../parallel/concrt/media/mandelbrot.png "Приложение "Мандельброт"")

Поскольку вычисления для каждого пикселя являются вычислительно дорогими, поток uI не может обрабатывать дополнительные сообщения до завершения общей вычислений. Это может снизить отзывчивость в приложении. Однако эту проблему можно снять, удалив работу из потока uI.

[Сверху](#top)

## <a name="removing-work-from-the-ui-thread"></a><a name="removing-work"></a>Удаление работы из нити uI

В этом разделе показано, как удалить работу рисования из потока uI в приложении Mandelbrot. Перемещая работу рисования из потока uI в рабочий поток, поток мизаносного использования может обрабатывать сообщения по мере того, как рабочий поток генерирует изображение в фоновом режиме.

В Concurrency Runtime предусмотрено три способа выполнения задач: [группы задач,](../../parallel/concrt/task-parallelism-concurrency-runtime.md) [асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)и [легкие задачи.](../../parallel/concrt/task-scheduler-concurrency-runtime.md) Хотя можно использовать любой из этих механизмов для удаления работы из потока uI, в этом примере используется [параллель::task_group](reference/task-group-class.md) объект, поскольку группы задач поддерживают отмену. Это пошаг-позднее использует отмену, чтобы уменьшить объем работы, выполняемой при повторном размере клиентского окна, и для выполнения очистки при разрушении окна.

В этом примере также используется [параллель::unbounded_buffer](reference/unbounded-buffer-class.md) объект, позволяющий потоку uI и потоку рабочего общаться друг с другом. После того, как рабочий поток создает изображение, `Bitmap` он `unbounded_buffer` отправляет указатель объекту объекту, а затем отправляет сообщение о краске в поток мигов. Затем поток uI получает `unbounded_buffer` от `Bitmap` объекта объект и притягивает его к клиенту.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>Удаление работы по рисованию из потока uI

1. В *pch.h* *(stdafx.h* в Visual Studio 2017 `#include` и ранее), добавьте следующие директивы:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. В ChildView.h `task_group` добавляйте переменные `unbounded_buffer` `protected` и члены в раздел `CChildView` класса. Объект `task_group` выполняет задачи, выполняющие рисунок; `unbounded_buffer` объект содержит завершенное изображение Мандельброта.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. В ChildView.cpp добавьте директиву `using` в `concurrency` пространство имен.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. В `CChildView::DrawMandelbrot` методе, после `Bitmap::UnlockBits`вызова, позвоните [в параллелизм::отправить](reference/concurrency-namespace-functions.md#send) функцию для передачи `Bitmap` объекта в поток uI. Затем разместите сообщение о краске в потоке uI и аннулируете область клиента.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Обновите `CChildView::OnPaint` метод `Bitmap` получения обновленного объекта и нарисуйте изображение к клиенту.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   Метод `CChildView::OnPaint` создает задачу для создания изображения Mandelbrot, если он не существует в буфере сообщения. Буфер сообщения не будет `Bitmap` содержать объект в таких случаях, как начальное сообщение краски и когда другое окно перемещается перед окном клиента.

1. Убедитесь, что приложение было успешно обновлено путем его создания и запуска.

Теперь uI более отзывчив, так как работа по рисованию выполняется в фоновом режиме.

[Сверху](#top)

## <a name="improving-drawing-performance"></a><a name="performance"></a>Улучшение производительности рисования

Поколение фрактала Mandelbrot является хорошим кандидатом для параллелизации, потому что вычисление каждого пикселя не зависит от всех других вычислений. Для параллелиза процедуры `for` рисования `CChildView::DrawMandelbrot` преобразуйте внешнюю петлю в методе в [колл-параллелизм::pарелэле для](reference/concurrency-namespace-functions.md#parallel_for) алгоритма, следующим образом.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Поскольку вычисление каждого элемента биткарты является независимым, вам не нужно синхронизировать операции рисования, которые получают доступ к памяти биткарты. Это позволяет масштабировать производительность по мере увеличения количества доступных процессоров.

[Сверху](#top)

## <a name="adding-support-for-cancellation"></a><a name="cancellation"></a>Добавление поддержки отмены

В этом разделе описывается, как обрабатывать размеры окон и как отменить любые активные задачи рисования при уничтожении окна.

В [документе Отмена в PPL](cancellation-in-the-ppl.md) объясняет, как отмена работает во время выполнения. Отмена является кооперативной; поэтому это происходит не сразу. Чтобы остановить отмененную задачу, время выполнения бросает внутреннее исключение во время последующего вызова из задачи в время выполнения. В предыдущем разделе показано, `parallel_for` как использовать алгоритм для повышения производительности задачи рисования. Вызов позволяет `parallel_for` времени выполнения остановить задачу и, следовательно, позволяет выполнять.

### <a name="cancelling-active-tasks"></a>Отмена активных задач

Приложение Mandelbrot `Bitmap` создает объекты, размеры которых соответствуют размеру клиентского окна. Каждый раз, когда клиентское окно переоценивается, приложение создает дополнительную фоновую задачу для создания изображения для нового размера окна. Приложение не требует этих промежуточных изображений; для этого требуется только изображение для окончательного размера окна. Чтобы предотвратить выполнение приложения этой дополнительной работы, можно отменить любые `WM_SIZE` активные задачи рисования в обработчиках сообщений для сообщений, `WM_SIZING` а затем перенести работу рисования после изменения размера окна.

Чтобы отменить активные задачи рисования при повторном размере окна, приложение вызывает [параллелизм::task_group:::отмена](reference/task-group-class.md#cancel) метода в обработчиках `WM_SIZING` и `WM_SIZE` сообщениях. Обработчик `WM_SIZE` сообщения также называет [параллелизм::task_group::метод ожидания,](reference/task-group-class.md#wait) чтобы выполнить все активные задачи, а затем переносит задачу рисования для обновленного размера окна.

При уничтожении окна клиента необходимо отменить любые активные задачи рисования. Отмена любых активных задач рисования гарантирует, что рабочие потоки не размещают сообщения в потоке uI после разрушения окна клиента. Приложение отменяет все активные задачи рисования в обработчике `WM_DESTROY` для сообщения.

### <a name="responding-to-cancellation"></a>Реагирование на отмену

Метод, `CChildView::DrawMandelbrot` выполняя задачу рисования, должен реагировать на отмену. Поскольку время выполнения использует обработку `CChildView::DrawMandelbrot` исключений для отмены задач, метод должен использовать механизм безопасности исключений, чтобы гарантировать, что все ресурсы правильно очищены. Этот пример использует шаблон *инициализации ресурсов* (RAII), чтобы гарантировать разблокировку битовой карты при отмене задачи.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Добавление поддержки отмены в приложении Mandelbrot

1. В ChildView.h, `protected` в разделе `CChildView` класса, добавляйте `OnSize`декларации для функций карты `OnSizing`сообщений. `OnDestroy`

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. В ChildView.cpp измените карту сообщений, `WM_SIZE`чтобы `WM_SIZING`содержать `WM_DESTROY` обработчики для , и сообщения.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Выполните метод `CChildView::OnSizing`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Выполните метод `CChildView::OnSize`. Этот метод отменяет все существующие задачи рисования и создает новую задачу рисования для обновленного размера окна клиента.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Выполните метод `CChildView::OnDestroy`. Этот метод отменяет все существующие задачи рисования.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. В ChildView.cpp определите `scope_guard` класс, который реализует шаблон RAII.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Добавьте следующий `CChildView::DrawMandelbrot` код к методу после `Bitmap::LockBits`вызова:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Этот код обрабатывает отмену `scope_guard` путем создания объекта. Когда объект покидает область, он разблокирует биты битовой карты.

1. Измените конец `CChildView::DrawMandelbrot` метода, `scope_guard` чтобы отклонить объект после разблокировки битовой карты, но перед отправкой сообщений в поток uI. Это гарантирует, что поток uI не будет обновлен до разблокировки битов битовой карты.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

1. Убедитесь, что приложение было успешно обновлено путем его создания и запуска.

При повторном размере окна работа по рисованию выполняется только для окончательного размера окна. Любые активные задачи рисования также отменяются при уничтожении окна.

[Сверху](#top)

## <a name="see-also"></a>См. также раздел

[Параллелизм Runtime Прохождение](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Приложения MFC для рабочего стола](../../mfc/mfc-desktop-applications.md)
