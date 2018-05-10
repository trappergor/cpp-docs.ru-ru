---
title: 'Как: использование функции parallel_invoke для написания программы параллельной сортировки | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53b9699c7ee5d2bd4775f2d6b97dc4d1c5155ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки
В этом документе описывается использование [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) алгоритм для повышения производительности алгоритма битонной сортировки. Алгоритм битонной сортировки рекурсивно разделяет входной последовательности на сортированные разделы меньшего размера. Алгоритма битонной сортировки могут выполняться параллельно, поскольку каждая операция разделения независима от других операций.  
  
 Несмотря на то, что битонной сортировки является примером *сети сортировки* , сортирует все сочетания входных последовательностей, в этом примере выполняется сортировка последовательностей, длина которых представляет возведения в квадрат.  
  
> [!NOTE]
>  В этом примере для демонстрации используется параллельная подпрограмма сортировки. Можно также использовать встроенные алгоритмы сортировки, предоставляемые PPL: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), и [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Дополнительные сведения см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="top"></a> Разделы  
 В этом документе описаны следующие задачи:  
  
- [Выполнение битонной сортировки](#serial)  
  
- [Использование функции parallel_invoke для выполнения битонной сортировки параллельно](#parallel)  
  
##  <a name="serial"></a> Выполнение битонной сортировки  
 Пример последовательного версию алгоритма битонной сортировки. `bitonic_sort` Функция разделяет последовательность на два раздела, сортирует эти разделы в противоположных направлениях и объединяет результаты. Эта функция вызывает два раза рекурсивно для сортировки каждой секции.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="parallel"></a> Использование функции parallel_invoke для выполнения битонной сортировки параллельно  
 В этом разделе описывается использование `parallel_invoke` алгоритм для параллельного выполнения алгоритма битонной сортировки.  
  
### <a name="procedures"></a>Процедуры  
  
##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Для параллельного выполнения алгоритма битонной сортировки  
  
1.  Добавить `#include` директив для файла заголовка ppl.h.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  Добавить `using` директивы `concurrency` пространства имен.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  Создайте новую функцию с именем `parallel_bitonic_mege`, которая использует `parallel_invoke` алгоритм для объединения последовательности параллельно, если имеется достаточное количество работы. В противном случае вызов `bitonic_merge` Чтобы объединить последовательности последовательно.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  Выполнить процесс, похожее на предыдущем шаге, но для `bitonic_sort` функции.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  Создайте перегруженную версию `parallel_bitonic_sort` функцию, которая сортирует массива в порядке возрастания.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 `parallel_invoke` Алгоритм снижает нагрузку, выполняя последний ряд задач в вызывающем контексте. Например, в `parallel_bitonic_sort` функции, первая задача выполняется в отдельном контексте, а вторая задача выполняется в вызывающем контексте.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 Следующий пример выполняет серийный номер и параллельные версии цикла алгоритма битонной сортировки. Пример консоль также выводится время, необходимое для выполнения каждого вычисления.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
serial time: 4353  
parallel time: 1248  
```  
  
 [[В начало](#top)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-bitonic-sort.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe parallel-bitonic-sort.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом примере используется `parallel_invoke` алгоритм вместо [concurrency::task_group](reference/task-group-class.md) потому времени существования каждой группы задач не выходит за пределы функции. Мы рекомендуем использовать `parallel_invoke` при можно, так как он имеет меньше выполнение ресурсов, чем `task group` объектов и поэтому позволяет написать более производительный код.  
  
 Параллельные версии некоторых алгоритмов высокую только в том случае, если имеется достаточный объем работы для выполнения. Например `parallel_bitonic_merge` функция вызывает последовательную версию, `bitonic_merge`, если в последовательности 500 элементов или меньше. Можно также запланировать общую стратегию сортировки на основании объем работы. Например может быть более эффективно использовать последовательной версии алгоритма быстрой сортировки, если массив содержит менее 500 элементов, как показано в следующем примере:  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 Как и в случае с другими параллельными алгоритмами, рекомендуется профиль и оптимизировать код соответствующим образом.  
  
## <a name="see-also"></a>См. также  
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)

