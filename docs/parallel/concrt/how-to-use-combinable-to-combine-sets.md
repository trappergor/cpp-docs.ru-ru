---
title: "Практическое руководство. Использование класса combinable для комбинирования наборов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс combinable, пример"
  - "объединение наборов с помощью класса combinable [среда выполнения с параллелизмом]"
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование класса combinable для комбинирования наборов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе показано, как использовать класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) для вычисления набора простых чисел.  
  
## Пример  
 В следующем примере дважды вычисляется набор простых чисел.  Результат каждого вычисления сохраняется в объекте [std::bitset](../Topic/bitset%20Class.md).  В примере набор простых чисел сначала вычисляется последовательно, а затем — параллельно.  В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.  
  
 В примере алгоритм [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) и объект `combinable` используются для создания локальных наборов потока.  Затем с помощью метода [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) локальные наборы потоков объединяются в конечный поток.  
  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
  **последовательное время: 312 мс**  
**параллельное время: 78 мс**   
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `parallel-combine-primes.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc parallel\-combine\-primes.cpp**  
  
## См. также  
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)   
 [Метод combinable::combine\_each](../Topic/combinable::combine_each%20Method.md)