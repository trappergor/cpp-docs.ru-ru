---
title: "Как: преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2964c629ce8a3a83799278ac822b589992b4995
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом
В этом примере показано, как преобразовать OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[для](../../parallel/openmp/reference/for-openmp.md) цикл, который выполняет обработку исключений, чтобы использовать механизм обработки исключений среды выполнения с параллелизмом.  
  
 В OpenMP исключение, возникающее в параллельной области необходимо перехвачено и обработано в одном регионе тем же потоком. Перехвачено исключение, которое экранирует параллельной области обработчик необработанных исключений, который завершает процесс по умолчанию.  
  

 В среде выполнения с параллелизмом, при создании исключения в теле рабочей функции, передаваемого в группу задач, таких как [concurrency::task_group](reference/task-group-class.md) или [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта, или для параллельного алгоритма, такие как [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), среда выполнения хранит это исключение и маршалирует его в контекст, ожидающий группы задач или алгоритма для завершения. Для групп задач, ожидающих контекст, в контекст, вызывающий [Concurrency::task_group:: wait](reference/task-group-class.md#wait), [Concurrency::structured_task_group:: wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), или [Concurrency::structured_task_group::](reference/structured-task-group-class.md#run_and_wait). Для параллельного алгоритма ожидающим является контекст, вызвавший этот алгоритм. Среда выполнения также останавливает все активные задачи, которые находятся в группе задач, включая задачи дочерних групп, и удаляет любые задачи, которые еще не запущен.  


  
## <a name="example"></a>Пример  
 В этом примере показано, как обрабатывать исключения в OpenMP `parallel` области и в вызове `parallel_for`. `do_work` Функция выполняет запрос выделения памяти, который заканчивается неудачей и создает исключение типа [std::bad_alloc](../../standard-library/bad-alloc-class.md). В версии, использующей OpenMP поток, который создает исключение, должен его перехватить. Другими словами в каждой итерации параллельного цикла OpenMP должна обрабатывать исключение. В версии, использующей среду выполнения с параллелизмом основной поток перехватывает исключение, созданное другим потоком.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Using OpenMP...  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
Using the Concurrency Runtime...  
An error of type 'class std::bad_alloc' occurred.  
```  
  
 В версии этого примера, использующей OpenMP исключение происходит в и обрабатывается в каждой итерации цикла. В версии, использующей среду выполнения с параллелизмом, среда выполнения хранит это исключение, останавливает все активные задачи, удаляет любые задачи, которые еще не запущен и маршалирует его в контекст, вызывающий `parallel_for`.  
  
 Если требуется, версии, использующей OpenMP завершается после возникновения исключения, чтобы сообщить другим итерации цикла, произошедшей ошибки можно использовать логический флаг. Как показано в примере в разделе [как: преобразование цикла OpenMP, использует отмены для использования среды выполнения с параллелизмом](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), последующие итерации бы ничего не делать, если флаг установлен. И наоборот Если требуется, цикл, использующий среду выполнения с параллелизмом продолжает работу после возникновения исключения, следует обрабатывайте исключение в основной части параллельного цикла, сам.  
  
 Другие компоненты среды выполнения с параллелизмом, например асинхронных агентов и упрощенных задач не передавать исключения. Вместо этого необработанные исключения перехватываются обработчик необработанных исключений, который завершает процесс по умолчанию. Дополнительные сведения об обработке исключений см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Дополнительные сведения о `parallel_for` и других параллельных алгоритмах см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `concrt-omp-exceptions.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc/OpenMP CL.exe concrt-omp-exceptions.cpp**  
  
## <a name="see-also"></a>См. также  
 [Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

