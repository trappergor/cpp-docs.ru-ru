---
title: Практическое руководство. Написание цикла parallel_for
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: 8d2d54e084652a8f34b125b96c3f502dd9cdb1fa
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008959"
---
# <a name="how-to-write-a-parallel_for-loop"></a>Практическое руководство. Написание цикла parallel_for

В этом примере показано, как использовать метод [Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) , чтобы вычислить произведение двух матриц.

## <a name="example-compute-the-product-of-two-matrices"></a>Пример. Вычисление произведения двух матриц

В следующем примере показана `matrix_multiply` функция, которая вычисляет произведение двух квадратных матриц.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example-compute-a-matrix-multiply-in-parallel"></a>Пример: вычисление матрицы умножение в параллельном режиме

В следующем примере показана `parallel_matrix_multiply` функция, которая использует `parallel_for` алгоритм для параллельного выполнения внешнего цикла.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

В этом примере внешний цикл параллелизуются только потому, что он выполняет достаточную работу, чтобы воспользоваться преимуществами дополнительных затрат на параллельную обработку. При параллелизации внутреннего цикла вы не получаете выигрыш в производительности, так как небольшой объем работы, выполняемый внутренним циклом, не позволяет преодолеть издержки при параллельной обработке. Таким образом, параллелизация только внешнего цикла является лучшим способом обеспечить максимальную выгоду от параллелизма в большинстве систем.

## <a name="example-finished-parallel_for-loop-code-sample"></a>Пример: завершен parallel_for пример кода цикла

Следующий более полный пример сравнивает производительность `matrix_multiply` функции и `parallel_matrix_multiply` функции.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем, `parallel-matrix-multiply.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc Параллел-Матрикс-мултипли. cpp**

## <a name="see-also"></a>См. также статью

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)
