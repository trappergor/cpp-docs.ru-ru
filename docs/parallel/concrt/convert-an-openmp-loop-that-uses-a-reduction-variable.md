---
title: Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: b58f6025c41091b39375c566d2c1d4b4798437b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633081"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом

В этом примере демонстрируется преобразование OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[для](../../parallel/openmp/reference/for-openmp.md) цикл, использующий [сокращения](../../parallel/openmp/reference/reduction.md) предложение для использования среды выполнения с параллелизмом.

OpenMP `reduction` предложение позволяет указать одну или несколько переменных частные для потока, которые применяются к операции сокращения в конце область параллельной обработки. OpenMP предопределяет набор операторов редукции. Должен иметь скалярный тип каждой переменной сокращения (например, `int`, `long`, и `float`). OpenMP также определяет несколько ограничений на использование переменные сокращения в параллельной области.

Библиотека параллельных шаблонов (PPL) предоставляет [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс, который предоставляет многократно используемых, локальную для потока хранилище, которое позволяет выполнять детализированные вычисления и объединять их результаты в итоговую результат. `combinable` Класс является шаблоном, воздействующей на скалярные и сложные типы. Чтобы использовать `combinable` класса, выполнения вложенных вычислений в тексте параллельные конструкции и вызова [Concurrency::combinable:: Combine](reference/combinable-class.md#combine) или [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) метод для получения окончательного результата. `combine` И `combine_each` каждого методы принимают *объединить функции* , указывающий, как объединить каждой пары элементов. Таким образом `combinable` класса не привязана к фиксированному набору операторов редукции.

## <a name="example"></a>Пример

В этом примере используется как OpenMP, так и среда выполнения с параллелизмом для вычисления суммы первых 35 чисел Фибоначчи.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

Дополнительные сведения о `combinable` , представлена в разделе [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `concrt-omp-fibonacci-reduction.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe/EHsc/OpenMP concrt-omp-fibonacci-reduction.cpp**

## <a name="see-also"></a>См. также

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

