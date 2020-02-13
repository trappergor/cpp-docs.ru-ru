---
title: Пошаговое руководство. Создание пользовательского блока сообщений
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: a29ed382d67b91443bd13e029af2a37c42ee834d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142830"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Пошаговое руководство. Создание пользовательского блока сообщений

В этом документе описывается создание пользовательского типа блока сообщений, который упорядочивает входящие сообщения по приоритету.

Несмотря на то что встроенные типы блоков сообщений предоставляют широкий спектр функций, можно создать собственный тип блока сообщений и настроить его в соответствии с требованиями приложения. Описание встроенных типов блоков сообщений, предоставляемых библиотекой асинхронных агентов, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, прочитайте следующие документы:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

## <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Разработка пользовательского блока сообщений](#design)

- [Определение класса priority_buffer](#class)

- [Полный пример](#complete)

## <a name="design"></a>Разработка пользовательского блока сообщений

Блоки сообщений участвуют в действиях отправки и получения сообщений. Блок сообщений, который отправляет сообщения, называется *исходным блоком*. Блок сообщений, принимающий сообщения, называется *целевым блоком*. Блок сообщений, который отправляет и получает сообщения, называется *блоком распространителя*. Библиотека агентов использует абстрактный класс [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) для представления исходных блоков и абстрактный класс [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) для представления целевых блоков. Типы блоков сообщений, выступающих в качестве источников, являются производными от `ISource`; типы блоков сообщений, которые действуют как целевые объекты, являются производными от `ITarget`.

Хотя тип блока сообщений можно наследовать непосредственно от `ISource` и `ITarget`, Библиотека агентов определяет три базовых класса, которые выполняют большую часть функциональных возможностей, общих для всех типов блоков сообщений, например, обработка ошибок и соединение блоков сообщений в безопасном режиме. Класс [Concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) является производным от `ISource` и отправляет сообщения в другие блоки. Класс [Concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) является производным от `ITarget` и получает сообщения от других блоков. Класс [Concurrency::p ropagator_block](../../parallel/concrt/reference/propagator-block-class.md) является производным от `ISource` и `ITarget` и отправляет сообщения в другие блоки и получает сообщения от других блоков. Мы рекомендуем использовать эти три базовых класса для управления сведениями об инфраструктуре, чтобы сосредоточиться на поведении блока сообщений.

Классы `source_block`, `target_block`и `propagator_block` являются шаблонами, параметризованными для типа, который управляет соединениями или связями между исходным и целевым блоками и типом, который управляет обработкой сообщений. Библиотека агентов определяет два типа, выполняющих Управление ссылками, [Concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) и [concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). Класс `single_link_registry` позволяет связать блок сообщений с одним источником или с одним целевым объектом. Класс `multi_link_registry` позволяет связать блок сообщений с несколькими источниками или с несколькими целевыми объектами. Библиотека агентов определяет один класс, который выполняет Управление сообщениями [Concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). Класс `ordered_message_processor` позволяет блокам сообщений обрабатывать сообщения в порядке их получения.

Чтобы лучше понять, как блоки сообщений связаны с их источниками и целями, рассмотрим следующий пример. В этом примере показано объявление класса [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) .

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

Класс `transformer` является производным от `propagator_block`и, следовательно, действует как как исходный блок, так и как целевой блок. Он принимает сообщения типа `_Input` и отправляет сообщения типа `_Output`. Класс `transformer` указывает `single_link_registry` как диспетчер связей для всех целевых блоков и `multi_link_registry` как диспетчер связей для любых исходных блоков. Таким образом, объект `transformer` может иметь до одного целевого объекта и неограниченного числа источников.

Класс, производный от `source_block`, должен реализовывать шесть методов: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message)и [resume_propagation](reference/source-block-class.md#resume_propagation). Класс, производный от `target_block`, должен реализовывать метод [propagate_message](reference/propagator-block-class.md#propagate_message) и при необходимости реализовать метод [send_message](reference/propagator-block-class.md#send_message) . Наследование от `propagator_block` функционально эквивалентно наследованию как `source_block`, так и `target_block`.

Метод `propagate_to_any_targets` вызывается средой выполнения для асинхронной или синхронной обработки любых входящих сообщений и распространения всех исходящих сообщений. Метод `accept_message` вызывается целевыми блоками для приема сообщений. Многие типы блоков сообщений, например `unbounded_buffer`, отправляют сообщения только первому целевому объекту, который получит его. Таким образом, он передает владение сообщения целевой. Другие типы блоков сообщений, такие как [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), предлагают сообщения каждому из целевых блоков. Таким образом, `overwrite_buffer` создает копию сообщения для каждой цели.

Методы `reserve_message`, `consume_message`, `release_message`и `resume_propagation` позволяют блокам сообщений участвовать в резервировании сообщений. Целевые блоки вызывают метод `reserve_message`, когда им предлагается сообщение и необходимо зарезервировать сообщение для последующего использования. После того как целевой блок резервирует сообщение, он может вызвать метод `consume_message` для использования этого сообщения или метода `release_message` для отмены резервирования. Как и в случае с методом `accept_message`, реализация `consume_message` может либо передать владение сообщением, либо вернуть копию сообщения. После того как целевой блок использует или освобождает зарезервированное сообщение, среда выполнения вызывает метод `resume_propagation`. Как правило, этот метод возобновляет распространение сообщений, начиная со следующего сообщения в очереди.

Среда выполнения вызывает метод `propagate_message` для асинхронной пересылки сообщения из другого блока в текущий блок. Метод `send_message` похож на `propagate_message`, за исключением того, что он синхронно, а не асинхронно, отправляет сообщение в целевые блоки. Реализация `send_message` по умолчанию отклоняет все входящие сообщения. Среда выполнения не вызывает ни одного из этих методов, если сообщение не передает необязательную функцию фильтра, связанную с целевым блоком. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

[[В начало](#top)]

## <a name="class"></a>Определение класса priority_buffer

Класс `priority_buffer` — это пользовательский тип блока сообщений, который упорядочивает входящие сообщения сначала по приоритету, а затем по порядку получения сообщений. Класс `priority_buffer` похож на класс [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , так как он содержит очередь сообщений, а также потому, что он действует как как исходный, так и целевой блок сообщений и может одновременно иметь несколько источников и несколько целевых объектов. Однако `unbounded_buffer` распространение сообщений выполняется только в том порядке, в котором он получает сообщения из своих источников.

Класс `priority_buffer` получает сообщения типа std::[Tuple](../../standard-library/tuple-class.md) , которые содержат элементы `PriorityType` и `Type`. `PriorityType` относится к типу, содержащему приоритет каждого сообщения; `Type` ссылается на часть данных сообщения. Класс `priority_buffer` отправляет сообщения типа `Type`. Класс `priority_buffer` также управляет двумя очередями сообщений: объектом [std::p riority_queue](../../standard-library/priority-queue-class.md) для входящих сообщений и объектом std::[Queue](../../standard-library/queue-class.md) для исходящих сообщений. Упорядочение сообщений по приоритету полезно, когда `priority_buffer` объект получает несколько сообщений одновременно или когда оно получает несколько сообщений перед чтением сообщений потребителями.

Помимо семи методов, которые должен реализовать класс, производный от `propagator_block`, класс `priority_buffer` также переопределяет методы `link_target_notification` и `send_message`. Класс `priority_buffer` также определяет два общедоступных вспомогательных метода, `enqueue` и `dequeue`, а также закрытый вспомогательный метод, `propagate_priority_order`.

В следующей процедуре описывается, как реализовать класс `priority_buffer`.

#### <a name="to-define-the-priority_buffer-class"></a>Определение класса priority_buffer

1. Создайте файл C++ заголовка и назовите его `priority_buffer.h`. Кроме того, можно использовать существующий файл заголовка, который является частью проекта.

1. В `priority_buffer.h`добавьте следующий код.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. В пространстве имен `std` определите специализации [std:: less](../../standard-library/less-struct.md) и [std:: больше](../../standard-library/greater-struct.md) , которые работают с объектами Concurrency::[Message](../../parallel/concrt/reference/message-class.md) .

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   Класс `priority_buffer` хранит объекты `message` в объекте `priority_queue`. Эти специализации типов позволяют очереди приоритетов сортировать сообщения в соответствии с их приоритетом. Приоритет — это первый элемент объекта `tuple`.

1. В пространстве имен `concurrencyex` объявите класс `priority_buffer`.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   Класс `priority_buffer` является производным от класса `propagator_block`. Поэтому он может отправлять и получать сообщения. Класс `priority_buffer` может иметь несколько целевых объектов, которые получают сообщения типа `Type`. Он также может иметь несколько источников, отправляющих сообщения типа `tuple<PriorityType, Type>`.

1. В разделе `private` класса `priority_buffer` добавьте следующие переменные члена.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   Объект `priority_queue` содержит входящие сообщения; Объект `queue` содержит исходящие сообщения. Объект `priority_buffer` может одновременно принимать несколько сообщений; Объект `critical_section` синхронизирует доступ к очереди входных сообщений.

1. В разделе `private` Определите конструктор копирования и оператор присваивания. Это предотвращает возможность назначения объектов `priority_queue`.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. В разделе `public` определите конструкторы, которые являются общими для многих типов блоков сообщений. Также определите деструктор.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. В разделе `public` Определите методы `enqueue` и `dequeue`. Эти вспомогательные методы предоставляют альтернативный способ отправки сообщений в объект `priority_buffer` и получения сообщений от него.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. В разделе `protected` Определите метод `propagate_to_any_targets`.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   Метод `propagate_to_any_targets` передает сообщение, находящийся в начале очереди ввода, в выходную очередь и распространяет все сообщения в очереди вывода.

10. В разделе `protected` Определите метод `accept_message`.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Когда целевой блок вызывает метод `accept_message`, класс `priority_buffer` передает владение сообщением первому целевому блоку, который его принимает. (Это напоминает поведение `unbounded_buffer`.)

11. В разделе `protected` Определите метод `reserve_message`.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   Класс `priority_buffer` позволяет целевому блоку резервировать сообщение, если предоставленный идентификатор сообщения совпадает с идентификатором сообщения, находящегося в начале очереди. Иными словами, цель может зарезервировать сообщение, если объект `priority_buffer` еще не получил дополнительное сообщение и еще не распространил его.

12. В разделе `protected` Определите метод `consume_message`.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Целевой блок вызывает `consume_message`, чтобы передавать владение зарезервированным сообщением.

13. В разделе `protected` Определите метод `release_message`.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Целевой блок вызывает `release_message`, чтобы отменить резервирование сообщения.

14. В разделе `protected` Определите метод `resume_propagation`.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Среда выполнения вызывает `resume_propagation` после того, как целевой блок использует или освобождает зарезервированное сообщение. Этот метод распространяет все сообщения, находящиеся в очереди вывода.

15. В разделе `protected` Определите метод `link_target_notification`.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor`ая переменная-член определяется базовым классом `source_block`. Эта переменная-член указывает целевому блоку, если таковой имеется, который удерживает резервирование для сообщения, находящегося в начале очереди вывода. Среда выполнения вызывает `link_target_notification`, когда новая цель связана с объектом `priority_buffer`. Этот метод распространяет все сообщения, находящиеся в очереди вывода, если цель не удерживает резервирование.

16. В разделе `private` Определите метод `propagate_priority_order`.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Этот метод распространяет все сообщения из очереди вывода. Каждое сообщение в очереди предлагается каждому целевому блоку до тех пор, пока один из целевых блоков не примет сообщение. Класс `priority_buffer` сохраняет порядок исходящих сообщений. Поэтому первое сообщение в очереди вывода должно быть принято целевым блоком перед тем, как этот метод предлагает другое сообщение целевым блокам.

17. В разделе `protected` Определите метод `propagate_message`.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   Метод `propagate_message` позволяет классу `priority_buffer` действовать как получатель сообщения или цель. Этот метод получает сообщение, предлагаемое предоставленным блоком источника, и вставляет это сообщение в очередь приоритетов. Затем метод `propagate_message` асинхронно отправляет все выходные сообщения в целевые блоки.

   Среда выполнения вызывает этот метод при вызове функции [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) или при соединении блока сообщений с другими блоками сообщений.

18. В разделе `protected` Определите метод `send_message`.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   Метод `send_message` напоминает `propagate_message`. Однако он отправляет выходные сообщения синхронно, а не асинхронно.

   Среда выполнения вызывает этот метод во время синхронной операции отправки, например при вызове функции [Concurrency:: send](reference/concurrency-namespace-functions.md#send) .

Класс `priority_buffer` содержит перегрузки конструктора, типичные для многих типов блоков сообщений. Некоторые перегрузки конструктора принимают объекты [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) , которые позволяют управлять блоком сообщений с помощью определенного планировщика заданий. Другие перегрузки конструктора принимают функцию Filter. Функции фильтрации позволяют блокам сообщений принимать или отклонять сообщения на основе полезных данных. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md). Дополнительные сведения о планировщиках задач см. в разделе [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Поскольку класс `priority_buffer` упорядочивает сообщения по приоритету, а затем по порядку получения сообщений, этот класс наиболее полезен при асинхронном получении сообщений, например при вызове функции [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) или при соединении блока сообщений с другими блоками сообщений.

[[В начало](#top)]

## <a name="complete"></a>Полный пример

В следующем примере показано полное определение класса `priority_buffer`.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

В следующем примере одновременно выполняется несколько `asend` и операций [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) для объекта `priority_buffer`.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

В этом примере выводится следующий пример выходных данных.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

Класс `priority_buffer` упорядочивает сообщения сначала по приоритету, а затем по порядку, в котором они получают сообщения. В этом примере сообщения с более высоким числовым приоритетом вставляются ближе к началу очереди.

[[В начало](#top)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте определение класса `priority_buffer` в файл с именем `priority_buffer.h` и программу тестирования в файл с именем `priority_buffer.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

**CL. exe/EHsc priority_buffer. cpp**

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
