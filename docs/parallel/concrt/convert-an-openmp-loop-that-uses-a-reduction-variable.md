---
title: Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: ee0a600f4234c3ebf4681ad92b5e3623be5665c3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141265"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом

В этом примере показано, как преобразовать [параллельный](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)цикл[for](../../parallel/openmp/reference/for-openmp.md) OpenMP, использующий предложение [reduction](../../parallel/openmp/reference/reduction.md) , для использования среда выполнения с параллелизмом.

Предложение OpenMP `reduction` позволяет указать одну или несколько частных переменных потока, которые подчиняются операции сокращения в конце параллельной области. OpenMP предопределяет набор операторов сокращения. Каждая переменная сокращения должна быть скалярной (например, `int`, `long`и `float`). OpenMP также определяет несколько ограничений на то, как переменные сокращения используются в параллельной области.

Библиотека Parallel Patterns (PPL) предоставляет класс [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) , который обеспечивает повторное использование, локальное хранилище потока, которое позволяет выполнять детализированные вычисления, а затем объединять эти вычисления в окончательный результат. Класс `combinable` — это шаблон, который действует как на скалярные, так и на сложные типы. Чтобы использовать класс `combinable`, выполните подвычисления в теле параллельной конструкции, а затем вызовите метод [Concurrency:: combinable:: Combine](reference/combinable-class.md#combine) или [Concurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) для получения конечного результата. Методы `combine` и `combine_each` принимают *функцию объединения* , которая определяет способ объединения каждой пары элементов. Таким образом, класс `combinable` не ограничен фиксированным набором операторов сокращения.

## <a name="example"></a>Пример

В этом примере используются OpenMP и среда выполнения с параллелизмом для вычисления суммы первых 35 чисел Фибоначчи.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

Дополнительные сведения о классе `combinable` см. в разделе [Parallel Containers and Objects](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `concrt-omp-fibonacci-reduction.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc/OpenMP конкрт-ОМП-фибонакЦи-редуктион. cpp**

## <a name="see-also"></a>См. также раздел

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)
