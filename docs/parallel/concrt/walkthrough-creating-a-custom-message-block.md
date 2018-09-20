---
title: 'Пошаговое руководство: Создание пользовательского блока сообщений | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9391d99f75bdb5ac2191a65e525ce989aefcd6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421288"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Пошаговое руководство. Создание пользовательского блока сообщений

В этом документе описывается, как создать пользовательский тип блока сообщений, сортирующий входящие сообщения по приоритету.

Несмотря на то, что встроенные типы блоков сообщений предоставляют широкий диапазон функций, можно создать собственный тип блока сообщений и настроить его в соответствии с требованиями вашего приложения. Описание встроенных типов блоков сообщений, предоставляемых библиотеки асинхронных агентов, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к этому руководству, приведены в следующих источниках:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Проектирование пользовательского блока сообщений](#design)

- [Определение priority_buffer класса](#class)

- [Полный пример](#complete)

##  <a name="design"></a> Проектирование пользовательского блока сообщений

Блоки сообщений участвовать в процесс отправки и получения сообщений. Блок сообщений, которое отправляет сообщения называется *блок источника*. Блок сообщений, получает сообщения называется *целевой блок*. Блок сообщений, отправляет и получает сообщения называется *мишени*. Библиотека агентов использует абстрактный класс [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) для представления блоков источника и абстрактный класс [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) целевые блоки. Типы блоков сообщений, выполняющие роль источников, являются производными от `ISource`; типы блоков сообщений, действующие как целевые объекты являются производными от `ITarget`.

Несмотря на то, что можно создавать производные ваш тип блока сообщений непосредственно из `ISource` и `ITarget`, библиотека агентов определяет три базовых классов, которые выполняют большинству функций, которые являются общими для всех типов блоков сообщений, например, обработка ошибок и подключения блоков сообщений друг к другу параллелизм безопасным образом. [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) класс является производным от `ISource` и отправляет сообщения другим блокам. [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) класс является производным от `ITarget` и принимает сообщения от других блоков. [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) класс является производным от `ISource` и `ITarget` и отправляет сообщения другим блокам и принимает сообщения от других блоков. Мы рекомендуем использовать эти три базовые классы для обработки сведений, инфраструктуры, что можно сосредоточиться на поведение своего блока сообщений.

`source_block`, `target_block`, И `propagator_block` классы являются шаблонами, которые параметризуются в тип, который управляет подключениями, или связями, между исходными и целевыми блоками и типом, который управляет обработкой сообщений. Библиотека агентов определяет два типа, выполняющих управление связями [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) и [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry` Класс позволяет блоку сообщений должны быть связаны одним источником or для одного целевого объекта. `multi_link_registry` Класс позволяет блоку сообщений связать несколько источников или несколько целевых объектов. Библиотека агентов определяет один класс, выполняющий управление сообщениями [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor` Класс позволяет блокам сообщений для обработки сообщений в порядке их получения.

Чтобы лучше понять, как блоки сообщений связаны с их исходные и целевые объекты, рассмотрим следующий пример. В этом примере показано объявление [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) класса.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` Класс является производным от `propagator_block`, поэтому он действует как блок источника и как целевой блок. Он принимает сообщения типа `_Input` и отправляет сообщения типа `_Output`. `transformer` Указывает класс `single_link_registry` диспетчер связи для любой целевым блокам и `multi_link_registry` диспетчер связи для любой блоков источника. Таким образом `transformer` объект может находиться до одного целевого объекта и неограниченного числа источников.

Класс, производный от `source_block` должен реализовывать методы шесть: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [ consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message), и [resume_propagation](reference/source-block-class.md#resume_propagation). Класс, производный от `target_block` должен реализовывать [propagate_message](reference/propagator-block-class.md#propagate_message) метод и при необходимости можно реализовать [send_message](reference/propagator-block-class.md#send_message) метод. Наследование от `propagator_block` функционально эквивалентен наследование от обоих `source_block` и `target_block`.

`propagate_to_any_targets` Метод вызывается средой выполнения для синхронно или асинхронно обрабатывать входящие сообщения и распространять исходящие сообщения. `accept_message` Метод вызывается целевым блокам для приема сообщений. Многие типы блоков сообщений, таких как `unbounded_buffer`, отправлять сообщения только первый целевой объект, который должен получить его. Таким образом он передает право владения сообщение целевому объекту. Другие типы блоков сообщений, таких как [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), предлагают сообщения всем своим целевым блокам. Таким образом `overwrite_buffer` создает копию сообщения для каждого из его целевых объектов.

`reserve_message`, `consume_message`, `release_message`, И `resume_propagation` методы позволяют блоки сообщений для участия в резервирование сообщений. Целевые блоки вызывают `reserve_message` метод, если они получают сообщение, которое нужно зарезервировать сообщение для последующего использования. После целевой блок резервирует сообщение, оно может вызвать `consume_message` метод для использования этого сообщения или `release_message` метод, чтобы отменить резервирование. Как и в `accept_message` метод, реализация `consume_message` можно передать права владения сообщения или возвращать копию сообщения. После целевой блок употребит или высвободит зарезервированное сообщение, среда выполнения вызывает `resume_propagation` метод. Как правило этот метод продолжает распространение сообщения, начиная со следующего сообщения в очереди.

Среда выполнения вызывает `propagate_message` метод асинхронно передавать сообщения от другого блока в текущий поток. `send_message` Похож на метод `propagate_message`, за исключением того, что оно синхронно, а не асинхронно, отправляет сообщение целевым блокам. Реализация по умолчанию `send_message` отклоняет все входящие сообщения. Среда выполнения не вызывает эти методы Если сообщение не проходит функцию дополнительный фильтр, который связан с целевым блоком. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

[[В начало](#top)]

##  <a name="class"></a> Определение priority_buffer класса

`priority_buffer` Класс является пользовательский тип блока сообщений, сортирующий входящие сообщения сначала по приоритету, а затем по порядку, в котором принимаются сообщения. `priority_buffer` Класс похож на [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) класса, так как он содержит очередь сообщений, а также так как он выступает в качестве источника и целевой блок сообщений и может иметь несколько источников и несколько целевые объекты. Тем не менее `unbounded_buffer` распространяет сообщения только на порядок, в котором оно получает сообщения из своих источников.

`priority_buffer` Класс получает сообщения типа std::[кортежа](../../standard-library/tuple-class.md) , содержащие `PriorityType` и `Type` элементы. `PriorityType` относится к типу, представляющему приоритет сообщения; `Type` ссылается на блок данных сообщения. `priority_buffer` Класс отправляет сообщения типа `Type`. `priority_buffer` Класс также управляет двумя очередями сообщений: [std::priority_queue](../../standard-library/priority-queue-class.md) объект для входящих сообщений и объект std::[очереди](../../standard-library/queue-class.md) объекта для исходящих сообщений. Сортировка сообщений по приоритету полезна, когда `priority_buffer` объект получает несколько сообщений одновременно, или при получении нескольких сообщений перед любой сообщения считываются потребителями.

Помимо семь методов, что класс, наследуемый от класса `propagator_block` должен реализовывать `priority_buffer` класса также переопределения `link_target_notification` и `send_message` методы. `priority_buffer` Класс также определяет два открытых вспомогательных метода, `enqueue` и `dequeue`и закрытый вспомогательный метод, `propagate_priority_order`.

Следующая процедура описывает способ реализации `priority_buffer` класса.

#### <a name="to-define-the-prioritybuffer-class"></a>Чтобы определить класс priority_buffer

1. Создайте файл заголовка C++ и назовите его `priority_buffer.h`. Кроме того можно использовать имеющийся файл заголовка, который является частью проекта.

1. В `priority_buffer.h`, добавьте следующий код.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. В `std` пространства имен, определите специализации структур [std::less](../../standard-library/less-struct.md) и [std::greater](../../standard-library/greater-struct.md) , действовать параллелизма::[сообщение](../../parallel/concrt/reference/message-class.md) объектов.

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

     The `priority_buffer` class stores `message` objects in a `priority_queue` object. These type specializations enable the priority queue to sort messages according to their priority. The priority is the first element of the `tuple` object.

1. В `concurrencyex` пространства имен, объявите `priority_buffer` класса.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

     The `priority_buffer` class derives from `propagator_block`. Therefore, it can both send and receive messages. The `priority_buffer` class can have multiple targets that receive messages of type `Type`. It can also have multiple sources that send messages of type `tuple<PriorityType, Type>`.

1. В `private` раздел `priority_buffer` добавьте следующие переменные-члены.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

     The `priority_queue` object holds incoming messages; the `queue` object holds outgoing messages. A `priority_buffer` object can receive multiple messages simultaneously; the `critical_section` object synchronizes access to the queue of input messages.

1. В `private` разделе, определять конструктор копии и оператор присваивания. Это предотвращает `priority_queue` назначать объекты.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. В `public` разделе, определять конструкторы, которые являются общими для многих типов блоков сообщений. Также можно определите деструктор.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. В `public` разделе, определяют методы `enqueue` и `dequeue`. Эти вспомогательные методы предоставляют альтернативный способ отправки и получения сообщений из `priority_buffer` объекта.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. В `protected` разделе, определить `propagate_to_any_targets` метод.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

     The `propagate_to_any_targets` method transfers the message that is at the front of the input queue to the output queue and propagates out all messages in the output queue.

10. В `protected` разделе, определить `accept_message` метод.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

     When a target block calls the `accept_message` method, the `priority_buffer` class transfers ownership of the message to the first target block that accepts it. (This resembles the behavior of `unbounded_buffer`.)

11. В `protected` разделе, определить `reserve_message` метод.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

     The `priority_buffer` class permits a target block to reserve a message when the provided message identifier matches the identifier of the message that is at the front of the queue. In other words, a target can reserve the message if the `priority_buffer` object has not yet received an additional message and has not yet  propagated out the current one.

12. В `protected` разделе, определить `consume_message` метод.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

     A target block calls `consume_message` to transfer ownership of the message that it reserved.

13. В `protected` разделе, определить `release_message` метод.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

     A target block calls `release_message` to cancel its reservation to a message.

14. В `protected` разделе, определить `resume_propagation` метод.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

     The runtime calls `resume_propagation` after a target block either consumes or releases a reserved message. This method propagates out any messages that are in the output queue.

15. В `protected` разделе, определить `link_target_notification` метод.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

     The `_M_pReservedFor` member variable is defined by the base class, `source_block`. This member variable points to the target block, if any, that is holding a reservation to the message that is at the front of the output queue. The runtime calls `link_target_notification` when a new target is linked to the `priority_buffer` object. This method propagates out any messages that are in the output queue if no target is holding a reservation.

16. В `private` разделе, определить `propagate_priority_order` метод.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

     This method propagates out all messages from the output queue. Every message in the queue is offered to every target block until one of the target blocks accepts the message. The `priority_buffer` class preserves the order of the outgoing messages. Therefore, the first message in the output queue must be accepted by a target block before this method offers any other message to the target blocks.

17. В `protected` разделе, определить `propagate_message` метод.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

     The `propagate_message` method enables the `priority_buffer` class to act as a message receiver, or target. This method receives the message that is offered by the provided source block and inserts that message into the priority queue. The `propagate_message` method then asynchronously sends all output messages to the target blocks.

     The runtime calls this method when you call the [concurrency::asend](reference/concurrency-namespace-functions.md#asend) function or when the message block is connected to other message blocks.

18. В `protected` разделе, определить `send_message` метод.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

     The `send_message` method resembles `propagate_message`. However it sends the output messages synchronously instead of asynchronously.

     The runtime calls this method during a synchronous send operation, such as when you call the [concurrency::send](reference/concurrency-namespace-functions.md#send) function.

`priority_buffer` Класс содержит перегрузки конструктора, обычные для многих типов блоков сообщений. Некоторые перегрузки конструкторов принимают [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объекты, позволяющие определенному планировщику задач управлять блоком сообщений. Другие перегрузки конструкторов принимают функцию фильтрации. Функции фильтрации позволяют блокам сообщений принимать или отклонять сообщения в зависимости от его полезные данные. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md). Дополнительные сведения о планировщиках задач см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Так как `priority_buffer` класс сортирует сообщения сначала по приоритету, а затем по порядку, в котором сообщения извлекаются, этот класс особенно полезен при асинхронном получении сообщений, например, при вызове [concurrency::asend](reference/concurrency-namespace-functions.md#asend)функции или при соединении блока сообщений с другими блоками сообщений.

[[В начало](#top)]

##  <a name="complete"></a> Полный пример

В следующем примере показано полное определение `priority_buffer` класса.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

В следующем примере параллельно выполняется несколько `asend` и [concurrency::receive](reference/concurrency-namespace-functions.md#receive) операции с `priority_buffer` объекта.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

В этом примере получается следующий результат.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer` Класс сортирует сообщения сначала по приоритету, а затем по порядку, в котором он получает сообщения. В этом примере сообщения с более высоким числовым приоритетом попадают в начале очереди.

[[В начало](#top)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или определение `priority_buffer` класса в файле с именем `priority_buffer.h` и тестовую программу — в файл с именем `priority_buffer.cpp` и затем выполните следующую команду в Visual Studio Окно командной строки.

**CL.exe priority_buffer.cpp/EHsc**

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
