---
title: "Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "среда выполнения с параллелизмом, использование с COM"
  - "COM, использование со средой выполнения с параллелизмом"
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе показывается, как использовать среду выполнения с параллелизмом в приложении, использующем модель COM.  
  
## Обязательные компоненты  
 Прежде чем начать выполнение этого пошагового руководства, необходимо ознакомиться со следующими документами.  
  
-   [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md)  
  
-   [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Обработка исключений](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)  
  
 Дополнительные сведения о COM см. в разделе [Модель COM](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## Управление временем существования библиотеки COM  
 Несмотря на то, что использование COM совместно со средой выполнения с параллелизмом базируется на тех же принципах, что и любой другой механизм параллелизма, следующие рекомендации могут помочь в эффективном совместном использовании этих библиотек.  
  
-   Поток должен вызвать метод [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) перед использованием библиотеки COM.  
  
-   Поток может вызывать метод `CoInitializeEx` несколько раз, если он предоставляет при вызовах одинаковые аргументы.  
  
-   При каждом вызове метода `CoInitializeEx` поток должен также выполнить вызов метода [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715).  Другими словами, вызовы методов `CoInitializeEx` и `CoUninitialize` должны быть сбалансированы.  
  
-   При переключении от одного потокового подразделения к другому поток должен полностью освободить библиотеку COM перед вызовом метода `CoInitializeEx` с новой потоковой спецификацией.  
  
 При использовании модели COM со средой выполнения с параллелизмом применяются и другие правила COM.  Например, приложение, создающее объект в однопотоковом подразделении \(STA\) и маршалирующее его в другое подразделение, должно также предоставить цикл сообщений для обработки входящих сообщений.  Также следует помнить, что маршалирование объектов между подразделениями может снизить производительность.  
  
### Использование COM с библиотекой параллельных шаблонов  
 При использовании COM в библиотеке параллельных шаблонов, например, с компонентом группы задач или параллельного алгоритма, следует вызвать метод `CoInitializeEx` перед использованием библиотеки COM для каждой задачи или итерации, и вызвать метод `CoUninitialize` до окончания каждой задачи или итерации.  Следующий пример показывает, как управлять временем жизни библиотеки COM с помощью объекта [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md).  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 Необходимо убедиться, что библиотека COM корректно освобождена при отмене задачи или параллельного алгоритма, или в том случае, если тело задачи породило исключение.  Чтобы гарантировать вызов задачей метода `CoUninitialize` до ее завершения, воспользуйтесь блоком `try-finally` или шаблоном *Получение ресурса есть инициализация* \(RAII\).  Следующий пример использует блок `try-finally` для освобождения библиотеки COM при завершении или отмене задачи, или при вызове исключения.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 В следующем примере используется шаблон RAII для определения класса `CCoInitializer`, который управляет временем жизни библиотеки COM в данной области.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 Можно воспользоваться классом `CCoInitializer` для автоматического освобождения библиотеки COM при завершении задачи, как показано далее.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 Дополнительные сведения об отмене в среде выполнения с параллелизмом см. в разделе [Отмена](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
### Использование COM с асинхронными агентами  
 При использовании COM с асинхронными агентами следует вызывать метод `CoInitializeEx` до использования библиотеки COM в методе [concurrency::agent::run](../Topic/agent::run%20Method.md) для вашего агента.  Затем необходимо вызвать метод `CoUninitialize` перед возвратом метода `run`.  Не используйте подпрограммы управления COM в конструкторе или деструкторе агента, не переопределяйте методы [concurrency::agent::start](../Topic/agent::start%20Method.md) или [concurrency::agent::done](../Topic/agent::done%20Method.md), так как эти методы вызываются из потока, отличного от потока, из которого вызывается метод `run`.  
  
 Следующий пример показывает базовый класс агентов с именем `CCoAgent`, который управляет библиотекой COM в методе `run`.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 Полный пример доступен далее в этом пошаговом руководстве.  
  
### Использование модели COM c упрощенными задачами  
 Документ [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md) описывает роль упрощенных задач в среде выполнения с параллелизмом.  Можно использовать модель COM с упрощенной задачей так же, как и с любой потоковой подпрограммой, передаваемой функции `CreateThread` в API Windows.  Это показано в следующем примере.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## Пример приложения с поддержкой COM  
 В этом разделе показано законченное приложение с поддержкой COM, которое использует интерфейс `IScriptControl` для выполнения скрипта, вычисляющего n\-ный член последовательности Фибоначчи.  Этот пример сначала вызывает скрипт из главного потока, а затем использует PPL и агенты для вызова скрипта в параллельном режиме.  
  
 Рассмотрим следующую вспомогательную функцию `RunScriptProcedure`, которая вызывает процедуру в объекте `IScriptControl`.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 Функция `wmain` создает объект `IScriptControl`, добавляет к нему код скрипта, вычисляющий n\-ный член последовательности Фибоначчи, а затем вызывает функцию `RunScriptProcedure` для запуска этого скрипта.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### Вызов скрипта из PPL  
 Следующая функция `ParallelFibonacci` использует алгоритм [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) для параллельного вызова скрипта.  Эта функция использует класс `CCoInitializer` для управления временем жизни библиотеки COM во время каждой итерации выполнения задачи.  
  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 Чтобы использовать функцию `ParallelFibonacci` с примером, добавьте до возврата функции `wmain` следующий код.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### Вызов скрипта из агента  
 Следующий пример показывает класс `FibonacciScriptAgent`, вызывающий процедуру скрипта для расчета n\-ного члена последовательности Фибоначчи.  Класс `FibonacciScriptAgent` использует отправку сообщений для получения из главной программы входных параметров для функции скрипта.  Метод `run` управляет временем жизни библиотеки COM на всем протяжении выполнения задачи.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 Следующая функция `AgentFibonacci` создает несколько объектов `FibonacciScriptAgent` и использует отправку сообщений для того, чтобы передать несколько входных значений этим объектам.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 Чтобы использовать функцию `AgentFibonacci` с примером, добавьте до возврата функции `wmain` следующий код.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### Полный код примера  
 Следующий код показывает полный пример, в котором для вызова скриптовой процедуры, вычисляющей числа Фибоначчи, используются параллельные алгоритмы и асинхронные агенты.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 В данном примере получается следующий результат.  
  
  **Главный поток:**  
**fib\(15\) \= 610**  
**Параллельный Фибоначчи:**  
**fib\(15\) \= 610**  
**fib\(10\) \= 55**  
**fib\(16\) \= 987**  
**fib\(18\) \= 2584**  
**fib\(11\) \= 89**  
**fib\(17\) \= 1597**  
**fib\(19\) \= 4181**  
**fib\(12\) \= 144**  
**fib\(13\) \= 233**  
**fib\(14\) \= 377**  
**Агент Фибоначчи:**  
**fib\(30\) \= 832040**  
**fib\(22\) \= 17711**  
**fib\(10\) \= 55**  
**fib\(12\) \= 144**   
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `parallel-scripts.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc parallel\-scripts.cpp \/link ole32.lib**  
  
## См. также  
 [Пошаговые руководства по среде выполнения с параллелизмом](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)   
 [Обработка исключений](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [Отмена](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)