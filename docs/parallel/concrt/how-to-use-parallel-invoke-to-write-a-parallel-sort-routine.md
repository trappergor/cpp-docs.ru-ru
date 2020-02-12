---
title: Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 6acac3f6bc82db6e6981f83715c7ee88cfd06fbd
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141930"
---
# <a name="how-to-use-parallel_invoke-to-write-a-parallel-sort-routine"></a>Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки

В этом документе описывается использование алгоритма [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) для повышения производительности алгоритма битонной сортировки. Алгоритм битонной сортировки рекурсивно разделяет входную последовательность на меньшие отсортированные секции. Алгоритм битонной сортировки может выполняться параллельно, так как каждая операция секционирования не зависит от других операций.

Хотя битонной сортировка является примером *сети сортировки* , которая сортирует все сочетания входных последовательностей, в этом примере сортируются последовательности, длина которых равна двум.

> [!NOTE]
> В этом примере для демонстрации используется параллельная подпрограмма сортировки. Можно также использовать встроенные алгоритмы сортировки, предоставляемые PPL: [Concurrency::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)и [Concurrency::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="top"></a> Разделы

В этом документе описаны следующие задачи.

- [Последовательный порядок выполнения битонной сортировки](#serial)

- [Использование parallel_invoke для выполнения битонной сортировки в параллельном режиме](#parallel)

## <a name="serial"></a>Последовательный порядок выполнения битонной сортировки

В следующем примере показана последовательная версия алгоритма битонной сортировки. Функция `bitonic_sort` разделяет последовательность на две секции, сортирует эти секции в противоположных направлениях, а затем объединяет результаты. Эта функция вызывает два раза рекурсивно для сортировки каждой секции.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[В начало](#top)]

## <a name="parallel"></a>Использование parallel_invoke для выполнения битонной сортировки в параллельном режиме

В этом разделе описывается использование алгоритма `parallel_invoke` для параллельного выполнения алгоритма битонной сортировки.

### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Параллельное выполнение алгоритма битонной сортировки

1. Добавьте директиву `#include` для файла заголовка PPL. h.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Добавьте директиву `using` для пространства имен `concurrency`.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Создайте новую функцию с именем `parallel_bitonic_mege`, которая использует алгоритм `parallel_invoke` для параллельного слияния последовательностей при наличии достаточного объема работы. В противном случае вызовите `bitonic_merge` для последовательного слияния последовательностей.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Выполните процесс, похожий на предыдущий шаг, но для функции `bitonic_sort`.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Создайте перегруженную версию функции `parallel_bitonic_sort`, которая сортирует массив по возрастанию.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

Алгоритм `parallel_invoke` сокращает затраты, выполняя последнюю последовательность задач в вызывающем контексте. Например, в функции `parallel_bitonic_sort` первая задача выполняется в отдельном контексте, а вторая задача выполняется в вызывающем контексте.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Следующий полный пример выполняет как последовательную, так и параллельную версии алгоритма битонной сортировки. Пример также выводит на консоль время, необходимое для выполнения каждого вычисления.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial time: 4353
parallel time: 1248
```

[[В начало](#top)]

### <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `parallel-bitonic-sort.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-битоник-сорт. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

В этом примере используется алгоритм `parallel_invoke` вместо класса [Concurrency:: task_group](reference/task-group-class.md) , так как время существования каждой группы задач не выходит за пределы функции. Рекомендуется использовать `parallel_invoke`, если это возможно, так как в нем меньше издержек на выполнение, чем `task group` объектов, и поэтому вы можете написать более эффективный код.

Параллельные версии некоторых алгоритмов работают лучше, только если достаточно работы. Например, функция `parallel_bitonic_merge` вызывает последовательную версию, `bitonic_merge`, если в последовательности 500 или меньше элементов. Вы также можете спланировать общую стратегию сортировки на основе объема работы. Например, использование последовательной версии алгоритма быстрой сортировки может оказаться более эффективным, если массив содержит менее 500 элементов, как показано в следующем примере:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Как и в случае с любым параллельным алгоритмом, рекомендуется пропрофилировать и настроить код соответствующим образом.

## <a name="see-also"></a>См. также раздел

[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)
