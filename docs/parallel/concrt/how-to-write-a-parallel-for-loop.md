---
title: 'Практическое: написание цикла parallel_for | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd9f10f473ae72c32b11fe648abe693568b34a6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395459"
---
# <a name="how-to-write-a-parallelfor-loop"></a>Практическое руководство. Написание цикла parallel_for

В этом примере демонстрируется использование [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) вычисляет произведение двух матриц.

## <a name="example"></a>Пример

В следующем примере показан `matrix_multiply` функцию, которая вычисляет произведение двух матриц квадрат.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example"></a>Пример

В следующем примере показан `parallel_matrix_multiply` функцию, которая использует `parallel_for` алгоритм для параллельного выполнения внешнего цикла.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

В этом примере параллелизуются внешний цикл, только в том случае, поскольку он выполняет мало работы, чтобы почувствовать преимущества параллельной обработки. Если распараллелить внутренний цикл не возникнет выигрыш в производительности так как небольшой объем работы, выполняемой во внутреннем цикле не позволяет компенсировать затраты на параллельную обработку. Таким образом, параллелизация только внешнего цикла является лучшим способом обеспечить максимальную выгоду от параллелизма в большинстве систем.

## <a name="example"></a>Пример

Следующие более полный пример сравнивает производительность `matrix_multiply` функции и `parallel_matrix_multiply` функции.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-matrix-multiply.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe параллельного matrix-multiply.cpp**

## <a name="see-also"></a>См. также

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)

