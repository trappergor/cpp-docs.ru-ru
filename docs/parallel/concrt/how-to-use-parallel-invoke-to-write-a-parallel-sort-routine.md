---
title: Практическое руководство. Использование функции parallel_invoke для написания параллельной сортировки
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 329cf275f283ba7b57276d06e909905c9a900697
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284181"
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Практическое руководство. Использование функции parallel_invoke для написания параллельной сортировки

В этом документе описывается использование [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) алгоритм для повышения производительности алгоритма битонной сортировки. Алгоритм битонной сортировки рекурсивно делит входной последовательности на сортированные разделы меньшего размера. Алгоритма битонной сортировки могут выполняться параллельно, так как каждая операция разделения не зависит от любых других операций.

Несмотря на то, что битонной сортировки является примером *сети сортировки* , сортирует все сочетания входных последовательностей, в этом примере выполняется сортировка последовательностей, длина которых представляет собой степень числа два.

> [!NOTE]
>  В этом примере для демонстрации используется параллельная подпрограмма сортировки. Можно также использовать встроенные алгоритмы сортировки, предоставляемые PPL: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), и [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Дополнительные сведения см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

##  <a name="top"></a> Разделы

В этом документе описаны следующие задачи:

- [Выполнение битонной сортировки](#serial)

- [Использование функции parallel_invoke для выполнения битонной сортировки в параллельном режиме](#parallel)

##  <a name="serial"></a> Выполнение битонной сортировки

В следующем примере последовательной версии алгоритма битонной сортировки. `bitonic_sort` Функция разделяет последовательность на два раздела, сортирует эти разделы в противоположных направлениях и объединяет результаты. Эта функция вызывает саму себя два раза рекурсивно для сортировки каждой секции.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[В начало](#top)]

##  <a name="parallel"></a> Использование функции parallel_invoke для выполнения битонной сортировки в параллельном режиме

В этом разделе описывается использование `parallel_invoke` алгоритм для параллельного выполнения алгоритма битонной сортировки.

### <a name="procedures"></a>Процедуры

##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Для параллельного выполнения алгоритма битонной сортировки

1. Добавление `#include` директив для файла заголовка ppl.h.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Добавить `using` директив для `concurrency` пространства имен.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Создайте новую функцию с именем `parallel_bitonic_mege`, которая использует `parallel_invoke` алгоритм слияния параллельно, если имеется достаточное количество работы. В противном случае вызовите `bitonic_merge` Чтобы объединить последовательности последовательно.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Выполняет процесс, отвечающий на предыдущем шаге, но для `bitonic_sort` функции.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Создать перегруженную версию `parallel_bitonic_sort` функцию, которая сортирует массива в порядке возрастания.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke` Алгоритм снижает нагрузку, выполняя последний ряд задач в вызывающем контексте. Например, в `parallel_bitonic_sort` функции, первая задача выполняется в отдельном контексте, а вторая задача выполняется в контексте вызова.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Приведенный ниже полный пример выполняет последовательных и параллельных версии алгоритма битонной сортировки. В примере также выводится на консоль время, необходимое для выполнения каждого вычисления.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial time: 4353
parallel time: 1248
```

[[В начало](#top)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-bitonic-sort.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe параллельного bitonic-sort.cpp**

## <a name="robust-programming"></a>Отказоустойчивость

В этом примере используется `parallel_invoke` алгоритм вместо [concurrency::task_group](reference/task-group-class.md) класса, так как время существования каждая группа задач не выходит за пределы функции. Мы рекомендуем использовать `parallel_invoke` при вы можете, поскольку в нем выполнении меньше ресурсов, чем `task group` объектов и поэтому позволяет написать более производительный код.

Параллельные версии некоторые алгоритмы работают лучше, только в том случае, если имеется достаточный объем работы для выполнения. Например `parallel_bitonic_merge` функция вызывает последовательную версию, `bitonic_merge`, если в последовательности более 500 элементов. Можно также запланировать общую стратегию сортировки на основании объема работы. Например может оказаться эффективнее использовать последовательной версии алгоритма быстрой сортировки, если массив содержит менее 500 элементов, как показано в следующем примере:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Как и в случае с другими параллельными алгоритмами, мы рекомендуем профилирования и оптимизации кода соответствующим образом.

## <a name="see-also"></a>См. также

[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)
