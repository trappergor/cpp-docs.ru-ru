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
ms.openlocfilehash: 6c4e2f27a6f123d870e56750180a5b7d4ee624fc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066413"
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

   `priority_buffer` Класса хранилищ `message` объекты в `priority_queue` объекта. Эти специализации типов позволяют очереди с приоритетом для сортировки сообщений в соответствии с их приоритетом. Приоритет — это первый элемент `tuple` объекта.

1. В `concurrencyex` пространства имен, объявите `priority_buffer` класса.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   Класс `priority_buffer` является производным от класса `propagator_block`. Таким образом он может отправлять и принимать сообщения. `priority_buffer` Класс может иметь несколько целевых объектов, которые получают сообщения типа `Type`. Он также может иметь несколько источников, которые отправляют сообщения типа `tuple<PriorityType, Type>`.

1. В `private` раздел `priority_buffer` добавьте следующие переменные-члены.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue` Объект хранит входящие сообщения; `queue` объект содержит исходящих сообщений. Объект `priority_buffer` объекта может получать несколько сообщений одновременно; `critical_section` объекта, выполняющего синхронизацию доступа к очереди входящих сообщений.

1. В `private` разделе, определять конструктор копии и оператор присваивания. Это предотвращает `priority_queue` назначать объекты.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. В `public` разделе, определять конструкторы, которые являются общими для многих типов блоков сообщений. Также можно определите деструктор.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. В `public` разделе, определяют методы `enqueue` и `dequeue`. Эти вспомогательные методы предоставляют альтернативный способ отправки и получения сообщений из `priority_buffer` объекта.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. В `protected` разделе, определить `propagate_to_any_targets` метод.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets` Метод передает сообщение, которое находится в передней части очереди ввода в очередь вывода и распространяет все сообщения в исходящей очереди.

10. В `protected` разделе, определить `accept_message` метод.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Когда целевой блок вызывает `accept_message` метода `priority_buffer` класс передает право владения сообщения в первый целевой блок, который принимает его. (Это напоминает поведение `unbounded_buffer`.)

11. В `protected` разделе, определить `reserve_message` метод.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer` Класс позволяет целевому блоку резервировать сообщение, если предоставленный идентификатор сообщения соответствует идентификатору сообщения, которое находится в передней части очереди. Другими словами, целевой объект можно зарезервировать сообщение, если `priority_buffer` объект еще не получил дополнительное сообщение и имеет не распространил текущего.

12. В `protected` разделе, определить `consume_message` метод.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Целевой блок вызывает `consume_message` для передачи владения сообщение, оно зарезервировано.

13. В `protected` разделе, определить `release_message` метод.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Целевой блок вызывает `release_message` отменить резервирование на сообщение.

14. В `protected` разделе, определить `resume_propagation` метод.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Среда выполнения вызывает `resume_propagation` после целевой блок употребит или освобождает зарезервированного сообщения. Этот метод распространяет все сообщения в исходящей очереди.

15. В `protected` разделе, определить `link_target_notification` метод.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` Переменную-член определяется базовым классом, `source_block`. Эта переменная-член указывает на целевой блок, если таковое имеется, который владеет резервирование к сообщению, расположенный в начале очереди вывода. Среда выполнения вызывает `link_target_notification` при новую цель связана с `priority_buffer` объекта. Этот метод распространяет все сообщения, которые находятся в очереди вывода, если нет целевых объектов, осуществляющих резервирование.

16. В `private` разделе, определить `propagate_priority_order` метод.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Этот метод распространяет все сообщения в исходящей очереди. Каждое сообщение в очереди предоставляется всем целевым блокам, пока один из блоков, целевой объект принимает сообщение. `priority_buffer` Класс сохраняет порядок исходящих сообщений. Таким образом первое сообщение в очереди вывода необходимо будет принят целевым блоком и, прежде чем этот метод предлагает все остальные сообщения целевым блокам.

17. В `protected` разделе, определить `propagate_message` метод.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message` Включает метод `priority_buffer` класса в качестве получателя сообщения или целевых. Этот метод получает сообщение, которое предоставляется в блоке предоставленного источника и вставляет его в очереди с приоритетом. `propagate_message` Метод асинхронно пересылает все исходящие сообщения целевым блокам.

   Среда выполнения вызывает этот метод при вызове [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функции или при соединении блока сообщений с другими блоками сообщений.

18. В `protected` разделе, определить `send_message` метод.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message` Похож на метод `propagate_message`. Тем не менее он отправляет исходящие сообщения синхронно, а не асинхронно.

   Среда выполнения вызывает этот метод во время операции синхронной отправки, например при вызове [concurrency::send](reference/concurrency-namespace-functions.md#send) функции.

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
