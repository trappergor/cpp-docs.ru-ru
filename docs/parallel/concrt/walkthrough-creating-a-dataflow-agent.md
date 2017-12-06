---
title: "Пошаговое руководство: Создание агента потоков данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b94fb68ad28e45141551b238acf99baedf78ef6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>Пошаговое руководство. Создание агента потоков данных
В этом документе показано, как создавать приложения на основе агентов, основанных на потока данных, а не потока управления.  
  
 *Поток управления* ссылается на порядок выполнения операций в программе. Поток управления контролируется с помощью структур управления, например условные инструкции, циклы и т. д. Кроме того *потока данных* ссылается на модель программирования, в которой вычисления выполняются, только когда доступна все необходимые данные. Модель программирования потоков данных связана с понятием передачи сообщений, в которой независимые компоненты программы взаимодействуют друг с другом посредством отправки сообщений.  
  
 Асинхронные агенты поддерживают потока управления и потока данных, модели программирования. Хотя во многих случаях подходит модели потока управления, модель потока данных подходит в других областях, например, когда агент получает данные и выполняет действие, основанный на полезные данные этих данных.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, приведены в следующих источниках:  
  
- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
##  <a name="top"></a> Разделы  
 Это пошаговое руководство содержит следующие разделы:  
  
- [Создание агента базовый поток управления](#control-flow)  
  
- [Создание основного агента потока данных](#dataflow)  
  
- [Создание агента ведения журнала сообщений](#logging)  
  
##  <a name="control-flow"></a>Создание агента базовый поток управления  
 Рассмотрим следующий пример, определяющий `control_flow_agent` класса. `control_flow_agent` Класс предназначен для трех буферов сообщений: одним входным буфером и два выходных буферов. `run` Метод считывает из исходного буфера сообщений в цикле и использует условный оператор, чтобы направить поток выполнения программы. Агент увеличивает один счетчик для отрицательных значений ненулевой а другого счетчика для положительных значений ненулевое значение. Когда агент получает нулевое значение-метку, он отправляет значения счетчиков буферам сообщений вывода. `negatives` И `positives` методы позволяют приложению считывать подсчет положительные и отрицательные значения от агента.  
  
 [!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]  
  
 Хотя этот пример делает использование потока управления в агенте, он демонстрирует последовательную природу программирования на основе потока управления. Каждое сообщение должно обрабатываться последовательно, даже если несколько сообщений может быть доступен на входном буфере. Модель потока данных позволяет обе ветви условного оператора для оценки одновременно. Модель потоков данных также позволяет создавать более сложные сети сообщений, которые работают с данными, как они станут доступны.  
  
 [[В начало](#top)]  
  
##  <a name="dataflow"></a>Создание основного агента потока данных  
 В этом разделе показано, как преобразовать `control_flow_agent` класса для использования модели потока данных для выполнения этой задачи.  
  
 Агент потока данных работает создает сеть буферов сообщений, каждый из которых служит определенной цели. Некоторые блоки сообщений используют функции фильтров для принятия или отклонения сообщения в зависимости от их полезной нагрузки. Функция фильтрации гарантирует, что блок сообщений получать только определенные значения.  
  
#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>Для преобразования потока управления агента для агента потоков данных  
  
1.  Скопируйте текст `control_flow_agent` класса в другой класс, например, `dataflow_agent`. Кроме того, можно переименовать `control_flow_agent` класса.  
  
2.  Удалить тело цикла, который вызывает `receive` из `run` метод.  
  
 [!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]  
  
3.  В `run` метод после инициализации переменных `negative_count` и `positive_count`, добавьте `countdown_event` объект, который отслеживает число активных операций.  
  
 [!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]  
  
     `countdown_event` Показано далее в этом разделе.  
  
4.  Создайте сообщение объекты буфера, который будет участвовать в сети потока данных.  
  
 [!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]  
  
5.  Соедините буферы сообщений, чтобы создать сеть.  
  
 [!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]  
  
6.  Дождитесь `event` и `countdown event` установки объектов. Эти события указывают, что агент получил значение-метку, и что все операции завершения.  
  
 [!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]  
  
 На следующей схеме показана полная сеть потока данных для `dataflow_agent` класса:  
  
 ![Сеть потока данных](../../parallel/concrt/media/concrt_dataflow.png "concrt_dataflow")  
  
 Следующая таблица описывает члены сети.  
  
|Член|Описание|  
|------------|-----------------|  
|`increment_active`|Объект [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) объект, который увеличивает счетчик активных событий и передает входное значение для остальных сетей.|  
|`negatives`, `positives`|[Concurrency::Call](../../parallel/concrt/reference/call-class.md) объектов, увеличивает число цифр и уменьшает счетчик активных событий. Все объекты используют фильтр принимать отрицательные или положительные числа.|  
|`sentinel`|Объект [concurrency::call](../../parallel/concrt/reference/call-class.md) объекта, который принимает только контрольного значения 0 и уменьшает счетчик активных событий.|  
|`connector`|Объект [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта, который подключается к внутренней сети исходного буфера сообщений.|  
  
 Поскольку `run` метод вызывается в отдельном потоке, другие потоки могут отправлять сообщения в сети, перед полностью подключение к сети. `_source` Член данных — `unbounded_buffer` объект, который помещает все входные данные, передаваемые от приложения к агенту. Чтобы убедиться в том, что сети обрабатывает все входные сообщения, агент сначала соединяет внутренние узлы сети, а затем соединяет начало этой сети, `connector`в `_source` элемент данных. Это гарантирует, что сообщения не обрабатываются как формируется сети.  
  
 Так как сеть в этом примере, основанной на потоке данных, вместо в потоке управления, сеть должна сообщать агенту о завершении обработки всех входных значений и что узел sentinel получил его значение. В этом примере используется `countdown_event` объект указывают, что все входные значения были обработаны и [concurrency::event](../../parallel/concrt/reference/event-class.md) объекте, чтобы указать, что соответствующий узел получил его значение. `countdown_event` Класс использует `event` объекта, чтобы сообщить, что значение счетчика достигло нуля. Начало сети потока данных увеличивает счетчик при каждом получении значения. Каждый конечный узел сети уменьшает счетчик после обработки входного значения. Когда агент формирует сеть потока данных, он ожидает sentinel узел, чтобы задать `event` объекта и для `countdown_event` объект указывают, что его счетчик достиг нуля.  
  
 В следующем примере показан `control_flow_agent`, `dataflow_agent`, и `countdown_event` классы. `wmain` Функция создает `control_flow_agent` и `dataflow_agent` объекта и использует `send_values` функции для отправки агентами последовательность случайных значений.  
  
 [!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]  
  
 В этом примере получается следующий результат:  
  
```Output  
Control-flow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
Dataflow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `dataflow-agent.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc потока данных — agent.cpp**  
  
 [[В начало](#top)]  
  
##  <a name="logging"></a>Создание агента ведения журнала сообщений  
 В следующем примере показан `log_agent` класс, который имеет вид `dataflow_agent` класса. `log_agent` Класс реализует асинхронный агент ведения журнала, записывает журнал сообщений в файл и на консоль. `log_agent` Класс позволяет приложению классифицировать сообщения на информационные, предупреждения или ошибки. Он также позволяет приложению задавать ли каждой категории журнала записывается в файл и/или в консоли. В этом примере все сообщения в файл журнала и только сообщения об ошибках выводятся на консоль.  
  
 [!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]  
  
 Этот пример записывает следующие данные в консоль.  
  
```Output  
error: This is a sample error message.  
```  
  
 Этот пример также создает файл log.txt, содержащий следующий текст.  
  
```Output  
info: ===Logging started.=== 
warning: This is a sample warning message.  
error: This is a sample error message.  
info: ===Logging finished.=== 
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `log-filter.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc / log-filter.cpp**  
  
 [[В начало](#top)]  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
