---
title: Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: e5e5207fe435e73df60b757d4f595aacbb70fe72
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414026"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью

В этом документе показано, как использовать функции [Concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc) и [Concurrency:: Free](reference/concurrency-namespace-functions.md#free) для повышения производительности памяти. Он сравнивает время, необходимое для изменения числа элементов массива в параллельном режиме для трех различных типов, каждый из которых указывает `new` `delete` операторы и.

`Alloc`Функции и `Free` наиболее полезны, когда несколько потоков часто вызывают `Alloc` и `Free` . Среда выполнения содержит отдельный кэш памяти для каждого потока; Таким образом, среда выполнения управляет памятью без использования блокировок или барьеров памяти.

## <a name="example-types-that-specify-new-and-delete-operators"></a>Пример. типы, задающих операторы new и DELETE

В следующем примере показаны три типа, каждый из которых `new` задает `delete` операторы и. `new_delete`Класс использует глобальные `new` `delete` операторы и, а `malloc_free` класс использует функции вызываемой среды [malloc](../../c-runtime-library/reference/malloc.md) выполнения C [free](../../c-runtime-library/reference/free.md) и функции, а `Alloc_Free` класс использует среда выполнения с параллелизмом `Alloc` и `Free` .

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example-swap-and-reverse_array-functions"></a>Пример: функции swap и reverse_array

В следующем примере показаны функции `swap` и `reverse_array`. `swap`Функция обменивается содержимым массива по указанным индексам. Она выделяет память из кучи для временной переменной. `reverse_array`Функция создает большой массив и подсчитывает время, необходимое для того, чтобы несколько раз обращаться к этому массиву в параллельном режиме.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example-wmain-function"></a>Пример: Функция wmain

В следующем примере показана `wmain` функция, вычисляющая время, необходимое для `reverse_array` работы функции в `new_delete` `malloc_free` типах, и `Alloc_Free` , каждая из которых использует другую схему выделения памяти.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="complete-code-example"></a>Полный пример кода

Полный пример приведен ниже.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

В этом примере выводится следующий пример выходных данных для компьютера с четырьмя процессорами.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

В этом примере тип, использующий `Alloc` функции и, `Free` обеспечивает лучшую производительность памяти, поскольку `Alloc` функции и `Free` оптимизированы для частого выделения и освобождения блоков памяти из нескольких потоков.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `allocators.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc распределителя. cpp**

## <a name="see-also"></a>См. также раздел

[Функции управления памятью](../../parallel/concrt/memory-management-functions.md)<br/>
[Функция Alloc](reference/concurrency-namespace-functions.md#alloc)<br/>
[Бесплатная функция](reference/concurrency-namespace-functions.md#free)
