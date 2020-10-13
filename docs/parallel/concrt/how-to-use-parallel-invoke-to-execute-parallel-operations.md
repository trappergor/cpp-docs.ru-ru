---
title: Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: 62781b2915704c4104bd7e8a13e48e43d81955c6
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008337"
---
# <a name="how-to-use-parallel_invoke-to-execute-parallel-operations"></a>Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций

В этом примере показано, как использовать алгоритм [параллелизма::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) для повышения производительности программы, выполняющей несколько операций с общим источником данных. Так как никакие операции не изменяют источник, они могут быть выполнены параллельно, простым образом.

## <a name="example-create-initialize-and-perform-operations-on-a-variable"></a>Пример: создание, инициализация и выполнение операций с переменной

Рассмотрим следующий пример кода, который создает переменную типа `MyDataType` , вызывает функцию для инициализации этой переменной, а затем выполняет несколько длинных операций над этими данными.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

Если `lengthy_operation1` функции, `lengthy_operation2` и не `lengthy_operation3` изменяют `MyDataType` переменную, эти функции могут выполняться параллельно без дополнительных изменений.

## <a name="example-run-previous-example-in-parallel"></a>Пример. Запуск предыдущего примера в параллельном режиме

В следующем примере предыдущий пример изменяется для параллельного выполнения. `parallel_invoke`Алгоритм выполняет каждую задачу в параллельном режиме и возвращает после завершения всех задач.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example-perform-multiple-operations-on-a-downloaded-file"></a>Пример. выполнение нескольких операций с загруженным файлом

В следующем примере загружается *"Илиада"* by Homer из Gutenberg.org и выполняется несколько операций над этим файлом. В примере сначала выполняется последовательная работа этих операций, а затем выполняются одни и те же операции параллельно.

[!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]

В этом примере выводится следующий пример выходных данных.

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

В этом примере `parallel_invoke` алгоритм используется для вызова нескольких функций, которые работают с одним и тем же источником данных. Алгоритм можно использовать `parallel_invoke` для параллельного вызова любого набора функций, а не только тех, которые работают с теми же данными.

Так как `parallel_invoke` алгоритм вызывает каждую рабочую функцию параллельно, ее производительность ограничена функцией, которая принимает наибольшее время на завершение (то есть если среда выполнения обрабатывает каждую функцию на отдельном процессоре). Если этот пример выполняет больше задач параллельно, чем количество доступных процессоров, на каждом процессоре может выполняться несколько задач. В этом случае производительность ограничивается группой задач, для завершения которой требуется наибольшее время.

Поскольку в этом примере выполняются три задачи параллельно, не следует рассчитывать на то, что производительность будет масштабироваться на компьютерах с более чем тремя процессорами. Чтобы повысить производительность, можно разбить наиболее длительные задачи на небольшие задачи и параллельно выполнять эти задачи.

Можно использовать `parallel_invoke` алгоритм вместо классов [Concurrency:: task_group](reference/task-group-class.md) и [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) , если не требуется поддержка отмены. Пример, сравнивающий использование `parallel_invoke` алгоритма и групп задач, см. [в разделе как использовать parallel_invoke для написания параллельной подпрограммы сортировки](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем, `parallel-word-mining.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc/MD/ДУНИКОДЕ/D_AFXDLL Параллел-Ворд-мининг. cpp**

## <a name="see-also"></a>См. также статью

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)
