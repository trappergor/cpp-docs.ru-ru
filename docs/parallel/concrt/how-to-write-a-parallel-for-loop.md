---
title: 'Как: написание цикла parallel_for | Документы Microsoft'
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
ms.openlocfilehash: d4f3121130cd4b2871e3e3df73dd4117f946caca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-write-a-parallelfor-loop"></a>Практическое руководство. Написание цикла parallel_for
В этом примере демонстрируется использование [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) для вычисления произведения двух матриц.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `matrix_multiply` функции, которая вычисляет произведение двух квадратных матриц.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан `parallel_matrix_multiply` функции, которая использует `parallel_for` алгоритм для параллельного выполнения внешнего цикла.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 В этом примере параллелизации внешнего цикла только в том случае, поскольку он выполняет достаточный объем работы, чтобы почувствовать преимущества параллельной обработки. При распараллеливании внутреннего цикла не появится прироста производительности, так как небольшой объем работы, которая выполняет внутреннего цикла не компенсировать издержки параллельной обработки. Таким образом, параллелизация только внешнего цикла является лучшим способом обеспечить максимальную выгоду от параллелизма в большинстве систем.  
  
## <a name="example"></a>Пример  
 Следующие более сложном примере сравнивается производительность `matrix_multiply` функции и `parallel_matrix_multiply` функции.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
serial: 3853  
parallel: 1311  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-matrix-multiply.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe parallel-matrix-multiply.cpp**  
  
## <a name="see-also"></a>См. также  
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)


