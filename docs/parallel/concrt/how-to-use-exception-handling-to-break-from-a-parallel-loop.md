---
title: "Как: использовать обработку исключений для выхода из параллельного цикла | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29140c339614e572733988bd7ca5e14561cee5dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Практическое руководство. Использование обработки исключений для выхода из параллельного цикла
В этом разделе показано, как для записи алгоритма поиска для базовой древовидной структуры.  
  
 Раздел [отмены](cancellation-in-the-ppl.md) объясняется роль отмены в библиотеке параллельных шаблонов. Использование обработки исключений является менее эффективным способом отмены параллельной работы, чем использование [Concurrency::task_group:: Cancel](reference/task-group-class.md#cancel) и [Concurrency::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) методы. Один сценарий, где использование обработки исключений для отмены работы то, при вызове стороннюю библиотеку, которая использует задачами или параллельными алгоритмами, но не предоставляет `task_group` или `structured_task_group` объекта для отмены.  

  
## <a name="example"></a>Пример  
 В следующем примере показано базовое `tree` тип, который содержит элемент данных и список дочерних узлов. В следующем разделе показано тело `for_all` метод, который рекурсивно выполняет рабочую функцию на каждом дочернем узле.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан `for_all` метод. Она использует [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для выполнения рабочей функции на каждом узле дерева в параллельном режиме.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана функция `search_for_value`, которая выполняет поиск значения в предоставленном объекте `tree`. Эта функция передает `for_all` метод рабочую функцию, которая создает исключение при обнаружении узла дерева, содержащего предоставленное значение.  
  
 Предполагается, что `tree` стороннюю библиотеку предоставляет класс и его нельзя изменять. В этом случае использование обработки исключений подходит из-за `for_all` метод не выполняет `task_group` или `structured_task_group` вызывающему объекту объект. Таким образом рабочая функция не может непосредственно отменить свою родительскую группу задач.  
  
 Когда рабочую функцию, чтобы группа задач создает исключение, среда выполнения останавливает все задачи, которые находятся в группе задач (включая все дочерние группы задач) и удаляет любые задачи, которые еще не запущен. `search_for_value` Функция использует `try` - `catch` блок, чтобы зафиксировать исключение и вывести результат на консоль.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере создается `tree` объекта и выполняется поиск нескольких значений в параллельном режиме. `build_tree` Функция показана далее в этом разделе.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 В этом примере используется [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритм для поиска значений в параллельном режиме. Дополнительные сведения об этом алгоритме см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Пример  
 Полный пример использует обработку исключений для поиска значений в базовой древовидной структуры.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 В этом примере получается следующий результат.  
  
```Output  
Found a node with value 32614.  
Found a node with value 86131.  
Did not find node with value 17522.  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `task-tree-search.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe задачи дерево search.cpp**  
  
## <a name="see-also"></a>См. также  
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Класс task_group](reference/task-group-class.md)   
 [Класс structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)   
 [Функция parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)


