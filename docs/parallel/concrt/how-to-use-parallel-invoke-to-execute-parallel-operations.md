---
title: Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: 2d4cd19a3cbb02b9c18b1733f8df6f64eb956803
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473688"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций

В этом примере показано, как использовать [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритм для повышения производительности программы, выполняющей несколько операций на общий источник данных. Так как операции не изменяет источник, они могут выполняться параллельно простым способом.

## <a name="example"></a>Пример

Рассмотрим следующий пример кода, который создает переменную типа `MyDataType`, вызывает функцию для инициализации этой переменной, а затем выполняет несколько длительных операций с этими данными.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

Если `lengthy_operation1`, `lengthy_operation2`, и `lengthy_operation3` функции не изменяют `MyDataType` переменной, эти функции могут выполняться параллельно без дополнительных изменений.

## <a name="example"></a>Пример

В следующем примере изменяется предыдущий пример для параллельного выполнения. `parallel_invoke` Алгоритм выполняет каждую задачу в параллельном режиме и возвращает управление после завершения всех задач.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example"></a>Пример

Следующий пример скачивает *Илиада* Гомера из gutenberg.org и выполняющей несколько операций этого файла. В примере сначала выполняются последовательно, а затем выполняет те же операции в параллельном режиме.

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

В этом примере используется `parallel_invoke` алгоритм для вызова нескольких функций, которые влияют на тот же источник данных. Можно использовать `parallel_invoke` алгоритм для вызова любого набора функций в параллельном режиме, не только те, которые работают с теми же данными.

Так как `parallel_invoke` алгоритм вызывает каждую функцию в параллельном режиме, ее производительность ограничивается функция, принимающая большое время (то есть, если среда выполнения обрабатывает каждую функцию в отдельном процессоре). Если этот пример выполняет несколько задач параллельно, чем число доступных процессоров, может выполняться несколько задач на каждый процессор. В этом случае производительность ограничивается группы задач, принимающий большое время.

Так как этот пример выполняет три задачи в параллельном режиме, не следует ожидать производительности для масштабирования на компьютерах с процессорами, более трех. Чтобы повысить производительность, можно разбить на более мелкие задачи продолжительные задачи и параллельного выполнения этих задач.

Можно использовать `parallel_invoke` алгоритм вместо [concurrency::task_group](reference/task-group-class.md) и [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) классы, если вам не требуется поддержка отмены. Пример, который сравнивает использование `parallel_invoke` алгоритм и группы задач, см. в разделе [как: использование функции parallel_invoke для написания параллельного сортировки](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-word-mining.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe/EHsc/MD/DUNICODE /D_AFXDLL параллельного word-mining.cpp**

## <a name="see-also"></a>См. также

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)

