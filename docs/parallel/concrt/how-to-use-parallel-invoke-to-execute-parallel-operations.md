---
title: 'Как: использование функции parallel_invoke для выполнения параллельных операций | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07c7a5248d5a132ae7b0542bfcedddee0c081753
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691174"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций
В этом примере показано, как использовать [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритм для повышения производительности программы, выполняющей несколько операций на общий источник данных. Так как нет операций не изменяет источник, они могут выполняться параллельно простым способом.  

  
## <a name="example"></a>Пример  
 Рассмотрим следующий пример кода, создает переменную типа `MyDataType`, вызывает функцию для инициализации этой переменной, а затем выполняет несколько продолжительных операций над этими данными.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 Если `lengthy_operation1`, `lengthy_operation2`, и `lengthy_operation3` функции не изменяют `MyDataType` переменной, эти функции могут выполняться параллельно, без дополнительных изменений.  
  
## <a name="example"></a>Пример  
 В следующем примере изменяется предыдущий пример для параллельного выполнения. `parallel_invoke` Алгоритм выполняет каждую задачу в параллельном режиме и возвращает управление после завершения всех задач.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере загружаются *Илиада* Гомера из gutenberg.org и выполняет несколько операций с этим файлом. В примере сначала выполняются последовательно и параллельно выполняет те же операции.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 В этом примере получается следующий результат.  
  
```Output  
Downloading 'The Iliad'...  
 
Running serial version... took 953 ms.  
Running parallel version... took 656 ms.  
 
The most common words that have five or more letters are:  
    their (953)  
    shall (444)  
    which (431)  
    great (398)  
    Hector (349)  
    Achilles (309)  
    through (301)  
    these (268)  
    chief (259)  
The longest sequence of words that have the same first letter is:  
    through the tempest to the tented  
The following palindromes appear in the text:  
    spots stops  
    speed deeps  
    keels sleek  
```  
  
 В этом примере используется `parallel_invoke` алгоритм для вызова нескольких функций, работающих на том же источнике данных. Можно использовать `parallel_invoke` алгоритм для вызова любого набора функций в параллельном режиме, не только те, которые действуют на тех же данных.  
  
 Поскольку `parallel_invoke` алгоритм вызывает каждую функцию параллельно, его эффективность ограничена функция, которая занимает самое большое время (если среда выполнения обрабатывает каждую функцию в отдельном процессоре). Если этот пример выполняет несколько задач в параллельном режиме, чем количество доступных процессоров, на каждом процессоре может выполняться несколько задач. В этом случае производительность ограничивается занимает самое большое время завершения группы задач.  
  
 Так как в этом примере параллельно выполняет три задачи, не стоит ожидать производительности для масштабирования на компьютерах, имеющих более трех процессоров. Чтобы повысить производительность, можно разбить на более мелкие задачи продолжительные задачи и параллельного выполнения этих задач.  
  
 Можно использовать `parallel_invoke` алгоритм вместо [concurrency::task_group](reference/task-group-class.md) и [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) классов, если не требуется поддержка отмены. Пример, который сравнивает использование `parallel_invoke` алгоритм и группы задач, в разделе [как: использование функции parallel_invoke для написания программы параллельной сортировки](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-word-mining.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/MD-DUNICODE /D_AFXDLL parallel-word-mining.cpp**  
  
## <a name="see-also"></a>См. также  
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)


