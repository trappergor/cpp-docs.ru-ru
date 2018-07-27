---
title: 'Как: использование функций Alloc и Free для повышения производительности памяти | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0be6fa309975663126331a7e38be0f2bea7dcf17
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686049"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью

В этом документе показано, как использовать [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) и [concurrency::Free](reference/concurrency-namespace-functions.md#free) функции для повышения производительности памяти. Он сравнивает время, которое требуется для отмены элементы массива в параллельном режиме для трех различных типов, каждый из которых задает `new` и `delete` операторы.  

  
 `Alloc` И `Free` функции наиболее полезны, когда несколько потоков часто вызывают обе `Alloc` и `Free`. Среда выполнения хранит отдельный кэш памяти для каждого потока; Поэтому среда выполнения управляет памятью без использования блокировки или барьеры памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере показано три типа, каждый из которых задает `new` и `delete` операторы. `new_delete` Класс использует глобальный `new` и `delete` операторы, `malloc_free` класс использует среды выполнения C [malloc](../../c-runtime-library/reference/malloc.md) и [свободного](../../c-runtime-library/reference/free.md) функции и `Alloc_Free` Среда выполнения с параллелизмом использует класс `Alloc` и `Free` функции.  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показаны функции `swap` и `reverse_array`. `swap` Функция меняет местами содержимое массива с указанными индексами. Он выделяет память из кучи для этой временной переменной. `reverse_array` Функция создает большой массив и вычисляет время, когда необходимо отменить этот массив несколько раз в параллельном режиме.  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан `wmain` функции, которая вычисляет время, необходимое для `reverse_array` функции для работы с `new_delete`, `malloc_free`, и `Alloc_Free` типы, каждый из которых использует различные схемы выделения памяти.  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## <a name="example"></a>Пример  
 Далее приведен полный пример.  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 В этом примере получается следующий результат для компьютера, который имеет четыре процессора.  
  
```Output  
Took 2031 ms with new/delete.  
Took 1672 ms with malloc/free.  
Took 656 ms with Alloc/Free.  
```  
  
 В этом примере тип, использующий `Alloc` и `Free` функции обеспечивает наивысшую производительность памяти, так как `Alloc` и `Free` оптимизированы для частого выделения и освобождения блоков памяти из нескольких потоки.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `allocators.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe allocators.cpp/EHsc**  
  
## <a name="see-also"></a>См. также  
 [Функции управления памятью](../../parallel/concrt/memory-management-functions.md)   
 [Функция Alloc](reference/concurrency-namespace-functions.md#alloc)   
 [Free-функция](reference/concurrency-namespace-functions.md#free)

