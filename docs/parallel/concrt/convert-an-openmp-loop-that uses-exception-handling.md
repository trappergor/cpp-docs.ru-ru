---
title: Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
ms.openlocfilehash: f47beb7deffa0511e707768d2a1a84f47e489d5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608407"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом

В этом примере демонстрируется преобразование OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[для](../../parallel/openmp/reference/for-openmp.md) цикл, который выполняет обработку исключений, чтобы использовать механизм обработки исключений среды выполнения с параллелизмом.

В OpenMP исключение, возникающее в параллельной области должны перехвачено и обработано в одном регионе тем же потоком. Экранирует область параллельной обработки, исключение перехватывается обработчиком необработанных исключений, который завершает процесс по умолчанию.

В среде выполнения с параллелизмом, при создании исключения в теле рабочей функции, передайте в группу задач, таких как [concurrency::task_group](reference/task-group-class.md) или [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта, или Чтобы параллельный алгоритм, например [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), среда выполнения хранит это исключение и маршалирует его в контекст, ожидающий группы задач или алгоритм для завершения. Для группы задач, ожидающим является контекст, который вызывает [Concurrency::task_group:: wait](reference/task-group-class.md#wait), [Concurrency::structured_task_group:: wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), или [Concurrency::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait). Для параллельного алгоритма ожидающим является контекст, вызвавший этот алгоритм. Среда выполнения также останавливает все активные задачи, которые находятся в группе задач, включая дочерние группы задач, и удаляет все задачи, которые еще не запущено.

## <a name="example"></a>Пример

В этом примере демонстрируется обработка исключений в OpenMP `parallel` регионе и в вызове `parallel_for`. `do_work` Функция выполняет запрос выделения памяти, который завершается неудачно и создает исключение типа [std::bad_alloc](../../standard-library/bad-alloc-class.md). В версии, использующей OpenMP поток, который создает исключение, должен его перехватить. Другими словами каждая итерация параллельного цикла OpenMP должна обрабатывать исключение. В версии, используется среда выполнения с параллелизмом основной поток перехватывает исключение, возникающее другим потоком.

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

В версию этого примера, который использует OpenMP исключение возникает в и обрабатывается в каждой итерации цикла. В версии, используется среда выполнения с параллелизмом, среда выполнения сохраняет исключение, останавливает все активные задачи, удаляет любые задачи, которые еще не запущен и маршалирует его в контекст, вызывающий `parallel_for`.

Если вам требуется, что версии, использующей OpenMP завершается после возникновения исключения, можно использовать логический флаг для обозначения для других итераций цикла, что произошла ошибка. Как показано в примере в разделе [как: преобразование цикла OpenMP, использует отмены для использования среды выполнения с параллелизмом](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), последующие итерации будут выполняться никакие действия, если этот флаг имеет значение. И наоборот Если требуется, что цикл, который использует среда выполнения с параллелизмом продолжает после возникновения исключения, обрабатывать исключение в теле параллельного цикла, сам.

Другие компоненты среды выполнения с параллелизмом, например асинхронных агентов и упрощенных задач не передавать исключения. Вместо этого необработанные исключения перехватываются обработчика необработанных исключений, который завершает процесс по умолчанию. Дополнительные сведения об обработке исключений см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Дополнительные сведения о `parallel_for` и другие параллельные алгоритмы, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `concrt-omp-exceptions.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc/OpenMP CL.exe concrt-omp-exceptions.cpp**

## <a name="see-also"></a>См. также

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

