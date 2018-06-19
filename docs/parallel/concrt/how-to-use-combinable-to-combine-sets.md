---
title: 'Как: использование класса combinable для комбинирования наборов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 689dacb98bc9f8053686a02414151b4982edca67
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695776"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Практическое руководство. Использование класса combinable для комбинирования наборов
В этом разделе показано, как использовать [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класса для вычисления набора простых чисел.  
  
## <a name="example"></a>Пример  
 В следующем примере вычисляется набор простых чисел в два раза. Каждого вычисления сохраняет результат в [std::bitset](../../standard-library/bitset-class.md) объекта. В примере сначала вычисляет набор последовательно и параллельно вычисляется. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.  
  
 В этом примере используется [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм и `combinable` для создания локальных наборов потока. Затем он использует [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) метод для объединения наборов локального потока в конечный.  

  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
serial time: 312 ms  
 
parallel time: 78 ms  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `parallel-combine-primes.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe parallel-combine-primes.cpp**  
  
## <a name="see-also"></a>См. также  
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)   
 [Метод combinable::combine_each](reference/combinable-class.md#combine_each)


