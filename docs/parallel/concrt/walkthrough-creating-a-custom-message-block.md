---
title: Пошаговое руководство. Создание пользовательского блока сообщений
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: 3386994dce68812cf3ed0852a24d8910cb903acf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368558"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Пошаговое руководство. Создание пользовательского блока сообщений

В этом документе описывается, как создать пользовательский тип блоков сообщений, который заказывает входящие сообщения по приоритету.

Хотя встроенные типы блоков сообщений обеспечивают широкий диапазон функциональных возможностей, вы можете создать свой собственный тип блока сообщений и настроить его в соответствии с требованиями приложения. Для описания встроенных типов блоков сообщений, предоставляемых Библиотекой Асинхронных Агентов, [см.](../../parallel/concrt/asynchronous-message-blocks.md)

## <a name="prerequisites"></a>Предварительные требования

Прочитайте следующие документы, прежде чем начать это пошаговое решение:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a>Разделы

Это пошаговое руководство содержит следующие разделы:

- [Разработка пользовательского блока сообщений](#design)

- [Определение класса priority_buffer](#class)

- [Полный пример](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a>Разработка пользовательского блока сообщений

Блоки сообщений участвуют в акте отправки и получения сообщений. Блок сообщений, отправляемый сообщения, известен как *блок источника.* Блок сообщений, который получает сообщения, известен как *целевой блок.* Блок сообщений, который отправляет и получает сообщения, известен как *блок распространения.* Библиотека агентов использует параллелизацию абстрактного [класса::ISource](../../parallel/concrt/reference/isource-class.md) для представления исходных блоков и параллелизма абстрактного [класса::ITarget](../../parallel/concrt/reference/itarget-class.md) для представления целевых блоков. Типы блоков сообщений, `ISource`которые действуют как источники, вытекают из; типы блоков сообщений, `ITarget`которые действуют в качестве целей, вытекают из .

Хотя вы можете получить тип `ISource` блока `ITarget`сообщений непосредственно из и, Библиотека агентов определяет три базовых класса, которые выполняют большую часть функциональности, которая является общей для всех типов блоков сообщений, например, обработка ошибок и подключение блоков сообщений вместе в параллел-безопасной манере. [Параллель::source_block](../../parallel/concrt/reference/source-block-class.md) класс происходит `ISource` от и отправляет сообщения другим блокам. [Параллель::target_block](../../parallel/concrt/reference/target-block-class.md) класс происходит `ITarget` от и получает сообщения от других блоков. [Параллелизм::pклассropagator-block](../../parallel/concrt/reference/propagator-block-class.md) происходит `ISource` `ITarget` от и отправляет сообщения другим блокам и получает сообщения из других блоков. Мы рекомендуем использовать эти три базовых класса для обработки деталей инфраструктуры, чтобы можно было сосредоточиться на поведении блока сообщений.

В `source_block` `target_block`,, `propagator_block` и классы шаблоны, которые параметры, на тип, который управляет соединениями, или ссылки, между исходными и целевыми блоками и на тип, который управляет, как сообщения обрабатываются. Библиотека агентов определяет два типа, которые выполняют управление ссылками, [параллелизм::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) и [параллел: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). Класс `single_link_registry` позволяет быть связанным блоком сообщений с одним источником или с одной целью. Класс `multi_link_registry` позволяет быть связанным блоком сообщений с несколькими источниками или несколькими целями. Библиотека агентов определяет один класс, который выполняет управление сообщениями, [параллелизм::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). Класс `ordered_message_processor` позволяет блокам сообщений обрабатывать сообщения в порядке, в котором они получаются.

Чтобы лучше понять, как блоки сообщений соотносятся с их источниками и целями, рассмотрим следующий пример. Этот пример показывает декларацию [параллелизма::класс трансформера.](../../parallel/concrt/reference/transformer-class.md)

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

Класс `transformer` происходит от `propagator_block`, и, следовательно, действует как исходный блок и как целевой блок. Он принимает сообщения `_Input` типа и отправляет `_Output`сообщения типа. Класс `transformer` определяется `single_link_registry` как менеджер ссылок для любых `multi_link_registry` целевых блоков и как менеджер ссылок для любых блоков исходных источников. Таким образом, `transformer` объект может иметь до одной цели и неограниченное количество источников.

Класс, который вытекает `source_block` из должны реализовать шесть методов: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message,](reference/source-block-class.md#reserve_message) [consume_message,](reference/source-block-class.md#consume_message) [release_message,](reference/source-block-class.md#release_message)и [resume_propagation](reference/source-block-class.md#resume_propagation). Класс, который вытекает из `target_block` должны реализовать метод [propagate_message](reference/propagator-block-class.md#propagate_message) и может дополнительно реализовать [send_message](reference/propagator-block-class.md#send_message) метод. Выражаясь `propagator_block` из функционально эквивалентно вытекающих `source_block` `target_block`из обоих и .

Метод `propagate_to_any_targets` вызывается временем выполнения для асинхронного или синхронного обработки любых входящих сообщений и распространения любых исходящих сообщений. Метод `accept_message` вызывается целевыми блоками для приема сообщений. Многие типы блоков `unbounded_buffer`сообщений, такие как, отправляют сообщения только первой цели, которая будет получать его. Таким образом, он передает право собственности на сообщение цели. Другие типы блоков сообщений, такие как [параллелизм::overwrite_buffer,](../../parallel/concrt/reference/overwrite-buffer-class.md)предлагают сообщения каждому из своих целевых блоков. Таким `overwrite_buffer` образом, создает копию сообщения для каждой из своих целей.

`reserve_message`Методы `consume_message` `release_message`и `resume_propagation` методы позволяют блокам сообщений участвовать в бронировании сообщений. Целевые блоки вызывают `reserve_message` метод, когда им предлагают сообщение, и должны зарезервировать сообщение для последующего использования. После того, как целевой блок `consume_message` зарезервирует сообщение, `release_message` он может вызвать метод, чтобы уничтожить это сообщение, или метод для отмены резервирования. Как и `accept_message` в случае `consume_message` с методом, реализация может либо передать право собственности на сообщение, либо вернуть копию сообщения. После того, как целевой блок либо потребляет, либо `resume_propagation` выпускает зарезервированное сообщение, время выполнения вызывает метод. Как правило, этот метод продолжает распространение сообщений, начиная со следующего сообщения в очереди.

Время выполнения вызывает `propagate_message` метод для асинхронной передачи сообщения из другого блока в текущий. Метод `send_message` `propagate_message`напоминает, за исключением того, что он синхронно, а не асинхронно, отправляет сообщение в целевые блоки. Реализация по `send_message` умолчанию отклоняет все входящие сообщения. Время выполнения не вызывает ни один из этих методов, если сообщение не проходит функцию дополнительного фильтра, связанную с целевым блоком. Для получения дополнительной информации о фильтрах сообщений [см.](../../parallel/concrt/asynchronous-message-blocks.md)

[Сверху](#top)

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a>Определение класса priority_buffer

Класс `priority_buffer` — это пользовательский тип блока сообщений, который заказывает входящие сообщения сначала по приоритету, а затем по порядку, в котором получаются сообщения. Класс `priority_buffer` напоминает [параллел: unbounded_buffer](reference/unbounded-buffer-class.md) класс, потому что он держит очередь сообщений, а также потому, что он действует как источник и целевой блок сообщения и может иметь как несколько источников и несколько целей. Тем `unbounded_buffer` не менее, основы распространения сообщений только на том порядке, в котором он получает сообщения из своих источников.

Класс `priority_buffer` получает сообщения типа std::[tuple,](../../standard-library/tuple-class.md) которые содержат `PriorityType` и `Type` элементы. `PriorityType`относится к типу, который имеет приоритет каждого сообщения; `Type` относится к части данных сообщения. Класс `priority_buffer` отправляет сообщения типа `Type`. Класс `priority_buffer` также управляет двумя очередями сообщений: объектом [std::priority'queue](../../standard-library/priority-queue-class.md) для входящих сообщений и std:: объект[очереди](../../standard-library/queue-class.md) для исходящих сообщений. Заказ сообщений по приоритету `priority_buffer` полезен, когда объект получает несколько сообщений одновременно или когда он получает несколько сообщений, прежде чем какие-либо сообщения читаются потребителями.

В дополнение к семи методам, которые должен `propagator_block` реализовать класс, полученный из них, `priority_buffer` класс также переопределяет `link_target_notification` и `send_message` методы. Класс `priority_buffer` также определяет два метода общественного помощника, `enqueue` и `dequeue`, `propagate_priority_order`и частный метод помощника, .

Следующая процедура описывает, `priority_buffer` как реализовать класс.

#### <a name="to-define-the-priority_buffer-class"></a>Определить класс priority_buffer

1. Создайте файл заголовка СЗ `priority_buffer.h`и назовите его. Кроме того, можно использовать существующий файл заголовка, который является частью вашего проекта.

1. В, `priority_buffer.h`добавить следующий код.

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. В `std` пространстве имен определите специализации [std::less](../../standard-library/less-struct.md) и [std::больше,](../../standard-library/greater-struct.md) которые действуют на параллелизм:: объекты[сообщений.](../../parallel/concrt/reference/message-class.md)

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   Класс `priority_buffer` хранит `message` объекты `priority_queue` в объекте. Эти специализации позволяют приоритетной очереди сортировать сообщения в соответствии с их приоритетом. Приоритетом является первый `tuple` элемент объекта.

1. В `concurrencyex` пространстве имен объявите `priority_buffer` класс.

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   Класс `priority_buffer` является производным от класса `propagator_block`. Таким образом, он может отправлять и получать сообщения. Класс `priority_buffer` может иметь несколько целей, которые получают сообщения типа. `Type` Он также может иметь несколько `tuple<PriorityType, Type>`источников, которые отправляют сообщения типа.

1. В `private` разделе `priority_buffer` класса добавьте следующие переменные членов.

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   Объект `priority_queue` содержит входящие сообщения; `queue` объект содержит исходящие сообщения. Объект `priority_buffer` может получать несколько сообщений одновременно; `critical_section` объект синхронизирует доступ к очереди входных сообщений.

1. В `private` разделе определите конструктор атлетии и оператора назначения. Это предотвращает `priority_queue` присвоение объектов.

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. В `public` разделе определите конструкторы, которые являются общими для многих типов блоков сообщений. Также определите деструктор.

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. В `public` разделе, определить `enqueue` методы `dequeue`и . Эти методы помощи предоставляют альтернативный способ отправки `priority_buffer` сообщений и получения сообщений от объекта.

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. В `protected` разделе определите `propagate_to_any_targets` метод.

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   Метод `propagate_to_any_targets` передает сообщение, наехаве в передней части входной очереди, в выходную очередь и распространяет все сообщения в выходной очереди.

1. В `protected` разделе определите `accept_message` метод.

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Когда целевой блок `accept_message` вызывает `priority_buffer` метод, класс передает право собственности на сообщение первому целевому блоку, который принимает его. (Это напоминает поведение `unbounded_buffer`.)

1. В `protected` разделе определите `reserve_message` метод.

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   Класс `priority_buffer` разрешает целевому блоку резервировать сообщение, когда предоставленный идентификатор сообщения соответствует идентификатору сообщения, находясь в передней части очереди. Другими словами, цель может зарезервировать сообщение, если `priority_buffer` объект еще не получил дополнительное сообщение и еще не распространил текущее.

1. В `protected` разделе определите `consume_message` метод.

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Целевой блок `consume_message` требует передачи права собственности на зарезервировало сообщение.

1. В `protected` разделе определите `release_message` метод.

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Целевой блок `release_message` требует отмены бронирования в сообщение.

1. В `protected` разделе определите `resume_propagation` метод.

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Время выполнения `resume_propagation` вызывается после того, как целевой блок либо потребляет, либо выпускает зарезервированное сообщение. Этот метод распространяет любые сообщения, которые находятся в очереди вывода.

1. В `protected` разделе определите `link_target_notification` метод.

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   Переменная `_M_pReservedFor` участника определяется базовым `source_block`классом, . Эта переменная участника указывает на целевой блок, если таковой имеется, который удерживает резервирование к сообщению, которое находится в передней части выходной очереди. Время выполнения `link_target_notification` вызывается при подключении `priority_buffer` новой цели к объекту. Этот метод распространяет любые сообщения, которые находятся в очереди вывода, если ни одна цель не удерживает резервирование.

1. В `private` разделе определите `propagate_priority_order` метод.

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Этот метод распространяет все сообщения из выходной очереди. Каждое сообщение в очереди предлагается каждому целевому блоку до тех пор, пока один из целевых блоков не примет сообщение. Класс `priority_buffer` сохраняет порядок исходящих сообщений. Таким образом, первое сообщение в выходной очереди должно быть принято целевым блоком, прежде чем этот метод предложит какое-либо другое сообщение целевым блокам.

1. В `protected` разделе определите `propagate_message` метод.

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   Метод `propagate_message` позволяет `priority_buffer` классу выступать в качестве получателя сообщений или цели. Этот метод получает сообщение, предлагаемое предоставленным исходным блоком, и вставляет это сообщение в очередь приоритетов. Затем `propagate_message` метод асинхронно отправляет все выходные сообщения в целевые блоки.

   Время выполнения вызывает этот метод при вызове [параллелизма::функция asend](reference/concurrency-namespace-functions.md#asend) или когда блок сообщения подключен к другим блокам сообщений.

1. В `protected` разделе определите `send_message` метод.

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   Метод `send_message` напоминает `propagate_message`. Однако он отправляет выходные сообщения синхронно, а не асинхронно.

   Время выполнения вызывает этот метод во время синхронной операции отправки, например, при вызове [параллелизма:::отправка](reference/concurrency-namespace-functions.md#send) функции.

Класс `priority_buffer` содержит перегрузки конструктора, характерные для многих типов блоков сообщений. Некоторые перегрузки конструктора принимают [параллель:::Расписание](../../parallel/concrt/reference/scheduler-class.md) или [параллел: объекты ScheduleGroup,](../../parallel/concrt/reference/schedulegroup-class.md) которые позволяют блоку сообщений управляться определенным планировщиком задач. Другие перегрузки конструктора принимают функцию фильтра. Функции фильтра позволяют блокам сообщений принимать или отклонять сообщение на основе его полезной нагрузки. Для получения дополнительной информации о фильтрах сообщений [см.](../../parallel/concrt/asynchronous-message-blocks.md) Для получения дополнительной информации [Task Scheduler](../../parallel/concrt/task-scheduler-concurrency-runtime.md)о планировщиках задач см.

Поскольку `priority_buffer` класс заказывает сообщения по приоритету, а затем по порядку, в котором получены сообщения, этот класс наиболее полезен, когда он получает сообщения асинхронно, например, когда вы вызываете [параллелизм::функция asend](reference/concurrency-namespace-functions.md#asend) или когда блок сообщения подключен к другим блокам сообщений.

[Сверху](#top)

## <a name="the-complete-example"></a><a name="complete"></a>Полный пример

Ниже приводится полное определение `priority_buffer` класса.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

Следующий пример одновременно выполняет ряд `asend` и [параллелизм::Получение](reference/concurrency-namespace-functions.md#receive) операций на объекте. `priority_buffer`

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

В этом примере приводится следующий вывод выборки.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

Класс `priority_buffer` заказывает сообщения сначала по приоритету, а затем по порядку, в котором он получает сообщения. В этом примере сообщения с большим числовым приоритетом вставляются в переднюю часть очереди.

[Сверху](#top)

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual `priority_buffer` Studio или вставьте `priority_buffer.h` определение класса в названный файл `priority_buffer.cpp` и тестовую программу в файле, который назван, а затем запустите следующую команду в окне команды Visual Studio.

**cl.exe /EHsc priority_buffer.cpp**

## <a name="see-also"></a>См. также раздел

[Параллелизм Runtime Прохождение](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
