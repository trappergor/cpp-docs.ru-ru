---
title: "Как: преобразование цикла OpenMP, использующего отмену для использования среды выполнения с параллелизмом | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3c4d37dfe5182e375e7581d6f5ef8188b922e5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего отмену для использования среды выполнения с параллелизмом
В некоторых параллельных циклах не требуют выполнения всех итераций. Например алгоритм, который выполняет поиск значения можно завершить работу, когда значение найдено. OpenMP не предоставляет механизм для выхода из параллельного цикла. Тем не менее можно использовать флаг или логическое значение для включения итерации цикла, чтобы указать, что решение найдено. Среда выполнения с параллелизмом предоставляет функциональность, позволяющую одной задаче отменять другие задачи, которые еще не запущен.  
  
 В этом примере показано, как преобразовать OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[для](../../parallel/openmp/reference/for-openmp.md) цикл, который не требуется для всех итераций для выполнения с использованием механизма отмены среды выполнения с параллелизмом.  
  
## <a name="example"></a>Пример  

 В этом примере используется как OpenMP, так и среда выполнения с параллелизмом для реализации параллельные версии [std::any_of](../../standard-library/algorithm-functions.md#any_of) алгоритма. В версии OpenMP в этом примере используется флаг для координации среди всех итераций параллельного цикла, что условие было выполнено. Версия, использующего среду выполнения с параллелизмом использует [Concurrency::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) метод для остановки общую операцию, при выполнении условия.  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 В версии, использующей OpenMP выполняются все итерации цикла, даже если флаг установлен. Кроме того Если у задачи есть дочерние задачи, флаг также бы быть доступны для этих дочерних задач, для передачи отмены. В среде выполнения с параллелизмом Если отменяется группа задач, среда выполнения отменяет все дерево работы, включая дочерние задачи. [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм использует задачи для выполнения работы. Таким образом когда одна итерация цикла отменяет корневую задачу, отменяется все дерево вычислений. При отмене дерева работы среда выполнения не запускает новые задачи. Однако среда выполнения позволяет задачи, которые уже запущены для завершения. Таким образом, в случае использования `parallel_for_each` алгоритма, активные итерации цикла могут очистить свои ресурсы.  
  
 В этом примере обе версии Если массив содержит более одной копии значение для поиска, несколько итераций цикла можно одновременно задавать результат и отменить всю операцию. Можно использовать примитив синхронизации, такие как критической секции, если проблемы требуется только одна задача выполняет работу, когда выполняется условие.  
  
 Также можно использовать обработку исключений для отмены задач, использующих PPL. Дополнительные сведения об отмене см. в разделе [Отмена в PPL](cancellation-in-the-ppl.md).  
  
 Дополнительные сведения о `parallel_for_each` и других параллельных алгоритмах см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `concrt-omp-parallel-any-of.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/OpenMP concrt-omp-parallel-any-of.cpp**  
  
## <a name="see-also"></a>См. также  
 [Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

