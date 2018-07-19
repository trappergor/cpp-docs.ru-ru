---
title: 'Пошаговое руководство: Использование среда выполнения с параллелизмом в приложениях с поддержкой модели COM | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd9f665f77ca5ae5311b034ee7afef6241ac489
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692552"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM
В этом документе показано, как использовать среду выполнения с параллелизмом в приложении, которое использует компонент модели объектов (COM).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, приведены в следующих источниках:  
  
- [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)  
  
- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
- [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 Дополнительные сведения о COM см. в разделе [объектов модели компонентов (COM)](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## <a name="managing-the-lifetime-of-the-com-library"></a>Управление временем существования библиотеки COM  
 Несмотря на то, что использование COM в среде выполнения с параллелизмом следует тем же принципам, как любой другой механизм параллелизма, следующие рекомендации помогут этих библиотек вместе эффективного использования.  
  
-   Поток должен вызвать [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) до начала использования библиотеки COM.  
  
-   Можно вызвать поток `CoInitializeEx` несколько раз при условии, что он предоставляет те же аргументы, для каждого вызова.  
  
-   Для каждого вызова `CoInitializeEx`, необходимо также вызвать поток [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715). Другими словами, вызовы `CoInitializeEx` и `CoUninitialize` должны быть сбалансированы.  
  
-   Перейти от одного потокового подразделения к другому, поток должен полностью освободить библиотеку COM перед вызовом `CoInitializeEx` с новой потоковой спецификацией.  
  
 Другим правилам COM, при использовании COM со средой выполнения с параллелизмом. Например приложение, которое создает объект в однопотоковом подразделении (STA) и маршалирует этот объект в другое подразделение необходимо также указать цикл обработки сообщений для обработки входящих сообщений. Также следует помните, что объекты между подразделениями маршалинг может привести к снижению производительности.  
  
### <a name="using-com-with-the-parallel-patterns-library"></a>Использование COM с библиотекой параллельных шаблонов  
 При использовании COM с компонентом в параллельных шаблонов библиотеки (PPL), например, группы задач или параллельный алгоритм, вызывать `CoInitializeEx` до использования библиотеки COM во время каждой задачи или итерации и вызова `CoUninitialize` до завершения каждой задачи или итерации . В следующем примере показано, как для управления временем жизни библиотеки COM с [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта.  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 Необходимо убедиться в библиотеки COM корректно освобождена при отмене задачи или параллельного алгоритма, или при создании исключения текст задачи. Чтобы гарантировать, что задача вызывает `CoUninitialize` до ее завершения, используйте `try-finally` блока или *Получение ресурса есть инициализация* шаблон (RAII). В следующем примере используется `try-finally` блока для освобождения библиотеки COM при завершении или отмене задачи или при возникновении исключения.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 В следующем примере шаблон RAII для определения `CCoInitializer` класс, который управляет временем жизни библиотеки COM в данной области.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 Можно использовать `CCoInitializer` класса для автоматического освобождения библиотеки COM при завершении задачи, как показано ниже.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 Дополнительные сведения об отмене в среде выполнения с параллелизмом см. в разделе [Отмена в PPL](cancellation-in-the-ppl.md).  
  
### <a name="using-com-with-asynchronous-agents"></a>Использование модели COM с асинхронными агентами  

 При использовании COM с асинхронными агентами вызывать `CoInitializeEx` до использования библиотеки COM в [Concurrency::agent:: Run](reference/agent-class.md#run) метод для агента. Затем вызовите `CoUninitialize` перед `run` возвращает метод. Не используйте подпрограммы управления COM в конструкторе или деструкторе агента, а не заменяют [Concurrency::agent:: Start](reference/agent-class.md#start) или [concurrency::agent:: сделать](reference/agent-class.md#done) методы, так как эти методы являются вызывается из другого потока, чем `run` метод.  

  
 В примере показан базовый класс агентов с именем `CCoAgent`, который управляет библиотекой COM в `run` метод.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 Полный пример предоставляется далее в этом пошаговом руководстве.  
  
### <a name="using-com-with-lightweight-tasks"></a>Использование COM с упрощенными задачами  
 Документ [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md) описывается роль упрощенных задач в среде выполнения с параллелизмом. Можно использовать модель COM с упрощенной задачей так же, как и с любой потоковой подпрограммой, передаваемой `CreateThread` функции в Windows API. Эти действия показаны в следующем примере.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## <a name="an-example-of-a-com-enabled-application"></a>Пример приложения с поддержкой COM  
 В этом разделе показано законченное приложение с поддержкой COM, которое использует `IScriptControl` интерфейс для выполнения скрипта, которая вычисляет n<sup>й</sup> числом Фибоначчи. В этом примере сначала вызывает скрипт из главного потока, а затем использует PPL и агенты для вызова скрипта одновременно.  
  
 Рассмотрим следующую вспомогательную функцию `RunScriptProcedure`, которая вызывает процедуру `IScriptControl` объекта.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 `wmain` Функция создает `IScriptControl` , добавляет код скрипта, вычисляет n его<sup>й</sup> число Фибоначчи, а затем вызывает `RunScriptProcedure` функция для запуска этого скрипта.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### <a name="calling-the-script-from-the-ppl"></a>Вызов скрипта из PPL  

 Следующая функция `ParallelFibonacci`, использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм для вызова скрипта в параллельном режиме. Эта функция использует `CCoInitializer` класса для управления временем жизни библиотеки COM во время каждой итерации выполнения задачи.  

  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 Для использования `ParallelFibonacci` работать с примером, добавьте следующий код перед `wmain` возврата функцией.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### <a name="calling-the-script-from-an-agent"></a>Вызов скрипта из агента  
 В следующем примере показан `FibonacciScriptAgent` класс, который вызывает процедуру сценария для вычисления n<sup>й</sup> числом Фибоначчи. `FibonacciScriptAgent` Класс использует отправку сообщений для получения из главной программы входных параметров для функции скрипта. `run` Метод управляет временем жизни библиотеки COM на всем протяжении задачи.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 Следующая функция `AgentFibonacci`, создается несколько `FibonacciScriptAgent` объектов и использует отправку сообщений для отправки нескольких входных значений для этих объектов.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 Для использования `AgentFibonacci` работать с примером, добавьте следующий код перед `wmain` возврата функцией.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### <a name="the-complete-example"></a>Полный пример  
 Ниже приведен полный пример, в котором используется для вызова процедуры скрипта, которая вычисляет числа Фибоначчи параллельными алгоритмами и асинхронными агентами.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 Пример выдает следующий результат.  
  
```Output  
Main Thread:  
fib(15) = 610  
 
Parallel Fibonacci:  
fib(15) = 610  
fib(10) = 55  
fib(16) = 987  
fib(18) = 2584  
fib(11) = 89  
fib(17) = 1597  
fib(19) = 4181  
fib(12) = 144  
fib(13) = 233  
fib(14) = 377  
 
Agent Fibonacci:  
fib(30) = 832040  
fib(22) = 17711  
fib(10) = 55  
fib(12) = 144  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `parallel-scripts.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/Link parallel-array-search.cpp ole32.lib**  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)   
 [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)

