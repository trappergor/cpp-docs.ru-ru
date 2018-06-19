---
title: 'Пошаговое руководство: Создание пользовательского блока сообщений | Документы Microsoft'
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
ms.openlocfilehash: fa70cf40851815ff92f01405d47015afd2e3e444
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694681"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Пошаговое руководство. Создание пользовательского блока сообщений
В этом документе описывается создание настраиваемого блочного типа сообщений, сортирующий входящие сообщения по приоритету.  
  
 Несмотря на то, что встроенные типы блоков сообщений предоставляют широкий диапазон функциональных возможностей, можно создать собственные типы блоков сообщений и настроить его в соответствии с требованиями приложения. Описание типов блоков встроенной сообщения, предоставляемые библиотекой асинхронных агентов см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, приведены в следующих источниках:  
  
- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
##  <a name="top"></a> Разделы  
 Это пошаговое руководство содержит следующие разделы:  
  
- [Проектирование пользовательского блока сообщений](#design)  
  
- [Определение priority_buffer класса](#class)  
  
- [Полный пример](#complete)  
  
##  <a name="design"></a> Проектирование пользовательского блока сообщений  
 Блоки сообщений принимают участие в отправки и получения сообщений. Блок сообщений, которая отправляет сообщения называется *блок источника*. Блок сообщений, получает сообщения, называется *целевой блок*. Блок сообщений, отправляющий и принимающий сообщения, называется *блоке распространения*. Библиотека агентов использует абстрактный класс [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) для представления исходных блоков и абстрактный класс [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) целевые блоки. Типы блоков сообщений, выполняющие роль источников, являются производными от `ISource`; типы блоков сообщений, выполняющие роль целевых объектов являются производными от `ITarget`.  
  
 Несмотря на то, что можно получить ваш тип блока сообщений напрямую из `ISource` и `ITarget`, библиотека агентов определяет три базовых классов, которые выполняют значительную часть функциональные возможности, общие для всех типов блоков сообщений, например, обработка ошибок и Соединение блоков сообщений друг с другом в виде параллельно безопасно. [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) класс является производным от `ISource` и отправляет сообщения другим блокам. [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) класс является производным от `ITarget` и получает сообщения от других блоков. [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) класс является производным от `ISource` и `ITarget` и отправляет сообщения другим блокам и принимает сообщения от других блоков. Мы рекомендуем использовать эти три базовые классы для обработки сведений, инфраструктуру, что можно сосредоточиться на поведение своего блока сообщений.  
  
 `source_block`, `target_block`, И `propagator_block` классы являются шаблонами, которые параметризуются на тип, который управляет соединениями, или связями, между исходными и целевыми блоками и на тип, который управляет обработкой сообщений. Библиотека агентов определяет два типа, выполняющих управление связями [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) и [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry` Класс позволяет блоку сообщений должна быть установлена связь по одному источнику или к одному целевому объекту. `multi_link_registry` Класс позволяет блоку сообщений должно быть связано с несколькими источниками или несколько целевых объектов. Библиотека агентов определяет один класс, который выполняет управление сообщениями [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor` Класс позволяет блокам сообщений обрабатывать сообщения в порядке их получения.  
  
 Чтобы лучше понять, как блоки сообщений связаны с их источники и целевые объекты, рассмотрим следующий пример. В этом примере показано объявление [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) класса.  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
 `transformer` Класс является производным от `propagator_block`, поэтому он действует как блок источника и как целевой блок. Он принимает сообщения типа `_Input` и отправляет сообщения типа `_Output`. `transformer` Указывает класс `single_link_registry` как управления связями для любых целевых блоков и `multi_link_registry` как диспетчер связи для любых исходных блоков. Таким образом `transformer` объект можно создать до одного целевого объекта и неограниченного количества источников.  
  

 Класс, производный от `source_block` необходимо реализовать шесть методов: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [ consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message), и [resume_propagation](reference/source-block-class.md#resume_propagation). Класс, производный от `target_block` необходимо реализовать [propagate_message](reference/propagator-block-class.md#propagate_message) метода и при необходимости можно реализовать [send_message](reference/propagator-block-class.md#send_message) метод. Наследование от `propagator_block` функционально эквивалентен наследование от обоих `source_block` и `target_block`.  


  
 `propagate_to_any_targets` Метод вызывается средой выполнения, чтобы асинхронно или синхронно обрабатывать входящие сообщения и распространять исходящие сообщения. `accept_message` Метод вызывается методом целевым блокам для приема сообщений. Многие типы блоков сообщений, таких как `unbounded_buffer`, отправлять сообщения только первый целевой объект, который получил бы. Таким образом он передает владение сообщением целевой объект. Другие типы блоков сообщений, таких как [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), предлагают сообщения всем своим целевым блокам. Таким образом `overwrite_buffer` создает копию сообщения для каждого из его целевых объектов.  
  
 `reserve_message`, `consume_message`, `release_message`, И `resume_propagation` методы позволяют блокам сообщений для участия в резервирование сообщений. Целевые блоки вызывают `reserve_message` метод, если они получают сообщение, которое нужно зарезервировать сообщение для последующего использования. После целевой блок резервирует сообщение, он может вызвать `consume_message` метод для получения этого сообщения или `release_message` метод отмены бронирования. Как и в `accept_message` метод, реализация `consume_message` можно передать права владения сообщения или возвращать копию сообщения. После того как целевой блок использует или освобождает зарезервированное сообщение, среда выполнения вызывает `resume_propagation` метод. Как правило этот метод продолжает распространение сообщения, начиная со следующего сообщения в очереди.  
  
 Среда выполнения вызывает метод `propagate_message` асинхронно передать сообщение из другого блока для текущего метода. `send_message` Похож на метод `propagate_message`, за исключением того, что синхронно, а не асинхронно, сообщение отправляется целевым блокам. Реализация по умолчанию `send_message` отклоняет все входящие сообщения. Среда выполнения не вызывает любой из этих методов, если сообщение не проходит необязательную функцию фильтрации, связанный с целевой блок. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 [[В начало](#top)]  
  
##  <a name="class"></a> Определение priority_buffer класса  
 `priority_buffer` Класс — это тип блока пользовательских сообщений, сортирующий входящие сообщения сначала по приоритету, а затем по порядку получения сообщений. `priority_buffer` Похож [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) так как он содержит очередь сообщений, а также так как он действует в качестве источника и целевой блок сообщений и может иметь несколько источников и несколько целевые объекты. Однако `unbounded_buffer` распространяет сообщения только в порядке, в котором он получает сообщения из своих источников.  
  
 `priority_buffer` Класс получает сообщения типа std::[кортежа](../../standard-library/tuple-class.md) , содержащие `PriorityType` и `Type` элементы. `PriorityType` относится к типу, представляющему приоритет сообщения; `Type` ссылается на часть данных сообщения. `priority_buffer` Класс отправляет сообщения типа `Type`. `priority_buffer` Класс также управляет двумя очередями сообщений: [std::priority_queue](../../standard-library/priority-queue-class.md) объекта для входящих сообщений и std::[очереди](../../standard-library/queue-class.md) объекта для исходящих сообщений. Сортировка сообщений по приоритету полезен, когда `priority_buffer` объект получает несколько сообщений одновременно, или при получении нескольких сообщений перед все сообщения будут прочитаны получателями.  
  
 В дополнение к методам семь, класс, производный от `propagator_block` необходимо реализовать `priority_buffer` класса также переопределения `link_target_notification` и `send_message` методы. `priority_buffer` Класс также определяет два открытых вспомогательных метода `enqueue` и `dequeue`и закрытый вспомогательный метод `propagate_priority_order`.  
  
 Следующая процедура описывает, как реализовать `priority_buffer` класса.  
  
#### <a name="to-define-the-prioritybuffer-class"></a>Чтобы определить класс priority_buffer  
  
1.  Создайте файл заголовка C++ и назовите его `priority_buffer.h`. Кроме того можно использовать имеющийся файл заголовка, который является частью проекта.  
  
2.  В `priority_buffer.h`, добавьте следующий код.  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  В `std` пространства имен, определите специализации структур [std::less](../../standard-library/less-struct.md) и [std::greater](../../standard-library/greater-struct.md) , работающие с параллелизмом::[сообщение](../../parallel/concrt/reference/message-class.md) объектов.  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]  
  
     `priority_buffer` Класса хранилищ `message` объекты в `priority_queue` объекта. Эти специализации типов позволяют очереди с приоритетом для сортировки сообщений в соответствии с их приоритетом. Приоритетом является первым элементом `tuple` объекта.  
  
4.  В `concurrencyex` пространства имен, объявите `priority_buffer` класса.  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]  
  
     Класс `priority_buffer` является производным от класса `propagator_block`. Таким образом его могут отправлять и получать сообщения. `priority_buffer` Класс может иметь несколько целевых объектов, которые получают сообщения типа `Type`. Он также может иметь несколько источников, отправляющих сообщения типа `tuple<PriorityType, Type>`.  
  
5.  В `private` раздел `priority_buffer` добавьте следующие переменные-члены.  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]  
  
     `priority_queue` Объект содержит входящие сообщения; `queue` объект содержит исходящих сообщений. Объект `priority_buffer` объект может одновременно получать несколько сообщений; `critical_section` объекта синхронизации доступа к очереди входящих сообщений.  
  
6.  В `private` статьи, определять конструктор копирования и оператор присваивания. Это предотвращает `priority_queue` назначать объекты.  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  В `public` статьи, определять конструкторы, которые являются общими для многих типов блоков сообщений. Также можно определите деструктор.  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  В `public` статьи, определяют методы `enqueue` и `dequeue`. Эти вспомогательные методы предоставляют альтернативный способ отправки и получения сообщений из `priority_buffer` объекта.  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. В `protected` статьи, определять `propagate_to_any_targets` метод.  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]  
  
     `propagate_to_any_targets` Метод передает сообщение, которое находится в начале входной очереди для очереди вывода и распространяет все сообщения в исходящей очереди.  
  
10. В `protected` статьи, определять `accept_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]  
  
     Когда целевой блок вызывает `accept_message` метода `priority_buffer` класса передает владение сообщения первой целевой блок, который принимает его. (Это напоминает поведение `unbounded_buffer`.)  
  
11. В `protected` статьи, определять `reserve_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]  
  
     `priority_buffer` Класс позволяет целевому блоку резервировать сообщение, если предоставленный идентификатор сообщения совпадает идентификатор сообщения, которое находится в начале очереди. Другими словами, целевой объект может зарезервировать сообщение, если `priority_buffer` объект еще не получил дополнительное сообщение и имеет не распространил за текущий год.  
  
12. В `protected` статьи, определять `consume_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]  
  
     Целевой блок вызывает `consume_message` для передачи владения зарезервированным сообщением.  
  
13. В `protected` статьи, определять `release_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]  
  
     Целевой блок вызывает `release_message` отменить резервирование сообщения.  
  
14. В `protected` статьи, определять `resume_propagation` метод.  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]  
  
     Среда выполнения вызывает метод `resume_propagation` после целевой блок потребляет или освобождает зарезервированное сообщение. Этот метод распространяет все сообщения в исходящей очереди.  
  
15. В `protected` статьи, определять `link_target_notification` метод.  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]  
  
     `_M_pReservedFor` Переменную-член определяется базовым классом `source_block`. Эта переменная-член указывает на целевой блок, если таковая имеется, осуществляющий резервирование сообщение, которое находится в начале очереди вывода. Среда выполнения вызывает метод `link_target_notification` при связан новый целевой объект `priority_buffer` объекта. Этот метод распространяет все сообщения в исходящей очереди, если нет целевых объектов, осуществляющих резервирование.  
  
16. В `private` статьи, определять `propagate_priority_order` метод.  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]  
  
     Этот метод распространяет все сообщения в исходящей очереди. Каждое сообщение в очереди предоставляется всем целевым блокам, пока один из целевых блоков принимает сообщение. `priority_buffer` Класса сохраняет порядок исходящих сообщений. Таким образом первое сообщение в очереди вывода должен принять целевой блок, прежде чем этот метод предоставляет все сообщения целевым блокам.  
  
17. В `protected` статьи, определять `propagate_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]  
  
     `propagate_message` Включает метод `priority_buffer` класса в качестве получателя сообщения или целевых. Этот метод получает сообщение, которое предлагается блоком указанного источника и вставляет его в очередь с приоритетом. `propagate_message` Метод асинхронно отправляет все исходящие сообщения целевым блокам.  
  

     Исполняющая среда вызывает этот метод при вызове [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функцию или когда блок сообщений соединяется с другими блоками сообщений.  

  
18. В `protected` статьи, определять `send_message` метод.  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]  
  
     `send_message` Похож на метод `propagate_message`. Однако он отправляет исходящие сообщения синхронно, а не асинхронно.  
  

     Исполняющая среда вызывает этот метод во время операции синхронной отправки, например при вызове [concurrency::send](reference/concurrency-namespace-functions.md#send) функции.  
  
 `priority_buffer` Класс содержит перегрузки конструктора, типичные для многих типов блоков сообщений. Некоторые перегрузки конструкторов принимают [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объектов, которые позволяют блока сообщений, управляемых с помощью определенного планировщика задач. Другие перегрузки конструкторов принимают функцию фильтрации. Функции фильтрации позволяют блокам сообщений принимать или отклонять сообщения в зависимости от их полезной нагрузки. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md). Дополнительные сведения о планировщиках заданий см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Поскольку `priority_buffer` класс сортирует сообщения сначала по приоритету, а затем по порядку, в котором сообщения принимаются, этот класс особенно полезен при асинхронном получении сообщений, например, при вызове [concurrency::asend](reference/concurrency-namespace-functions.md#asend)функцию или когда блок сообщений соединяется с другими блоками сообщений.  
  
 [[В начало](#top)]  
  
##  <a name="complete"></a> Полный пример  
 В следующем примере показано полное определение `priority_buffer` класса.  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]  
  
 В следующем примере параллельно выполняется несколько `asend` и [concurrency::receive](reference/concurrency-namespace-functions.md#receive) операции над `priority_buffer` объекта.  

  
 [!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]  
  
 В этом примере получается следующий результат.  
  
```Output  
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36  
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12  
```  
  
 `priority_buffer` Класс сортирует сообщения сначала по приоритету, а затем по порядку, в котором он получает сообщения. В этом примере сообщения с более высоким числовым приоритетом попадают в начало очереди.  
  
 [[В начало](#top)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или скопируйте определение `priority_buffer` класс в файл с именем `priority_buffer.h` а тестовую программу — в файл с именем `priority_buffer.cpp` , а затем запустите следующую команду в Visual Studio Окно командной строки.  
  
 **CL.exe priority_buffer.cpp/EHsc**  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
