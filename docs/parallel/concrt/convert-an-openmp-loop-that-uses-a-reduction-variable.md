---
title: 'Как: преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0191f88eea47d21c730172ddb3594db7655006ca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом
В этом примере показано, как преобразовать OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[для](../../parallel/openmp/reference/for-openmp.md) цикл, использующий [сокращения](../../parallel/openmp/reference/reduction.md) предложение следует использовать среду выполнения с параллелизмом.  
  
 OpenMP `reduction` предложение позволяет указать один или несколько переменных частные для потока, которые применяются к операции редукции в конце параллельной области. OpenMP определяется готовый набор операторов редукции. Все переменные редукции должны быть скалярными (например, `int`, `long`, и `float`). OpenMP также определяет несколько ограничений на использование переменных редукции в параллельной области.  
  
 Библиотека параллельных шаблонов (PPL) предоставляет [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс, который предоставляет хранилище для повторного использования, локальных для потока, которое позволяет выполнять детализированные вычисления и объединять их в итоговый результат. `combinable` Класс — это шаблон, работающий на скалярные и сложные типы. Для использования `combinable` класса, выполнить вложенные вычисления в теле параллельной конструкции и вызова [Concurrency::combinable::](reference/combinable-class.md#combine) или [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) метод для получения окончательного результата. `combine` И `combine_each` каждого методы принимают *объединение функция* , указывает, как объединять пары элементов. Таким образом `combinable` класса не ограничивается фиксированный набор операторов редукции.  
  
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
  
 Дополнительные сведения о `combinable` см. в описании [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `concrt-omp-fibonacci-reduction.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/OpenMP concrt-omp Фибоначчи reduction.cpp**  
  
## <a name="see-also"></a>См. также  
 [Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

