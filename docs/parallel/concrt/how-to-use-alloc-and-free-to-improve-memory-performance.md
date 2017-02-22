---
title: "Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Alloc и Free, использование [среда выполнения с параллелизмом]"
  - "Использование функций Alloc и Free [среда выполнения с параллелизмом]"
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе показано, как использовать функции [concurrency::Alloc](../Topic/Alloc%20Function.md) и [concurrency::Free](../Topic/Free%20Function.md) для повышения производительности памяти.  В нем сравнивается время, необходимое для параллельного изменения порядка элементов массива на обратный для трех различных типов, каждый из которых задает операторы `new` и `delete`.  
  
 Функции `Alloc` и `Free` наиболее полезны, когда несколько потоков часто вызывают обе функции `Alloc` и `Free`.  Среда выполнения хранит отдельный кэш памяти для каждого потока; поэтому среда выполнения управляет памятью без использования блокировок или барьеров в памяти.  
  
## Пример  
 В следующем примере показаны три типа, каждый из которых задает операторы `new` и `delete`.  В классе `new_delete` используются глобальные операторы `new` и `delete`, в классе `malloc_free` используются функции [malloc](../../c-runtime-library/reference/malloc.md) и [free](../../c-runtime-library/reference/free.md) среды выполнения C, а в классе `Alloc_Free` используются функции `Alloc` и `Free` среды выполнения с параллелизмом.  
  
 [!CODE [concrt-allocators#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#1)]  
  
## Пример  
 В следующем примере показаны функции `swap` и `reverse_array`.  Функция `swap` меняет местами содержимое массива с указанными индексами.  Она выделяет память для временной переменной из кучи.  Функция `reverse_array` создает большой массив и вычисляет время, необходимое для того, чтобы несколько раз изменить порядок элементов этого массива на обратный в параллельном режиме.  
  
 [!CODE [concrt-allocators#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#2)]  
  
## Пример  
 В следующем примере показана функция `wmain`, вычисляющая время, необходимое функции `reverse_array` для работы с типами `new_delete`, `malloc_free` и `Alloc_Free`, каждый из которых использует различные схемы выделения памяти.  
  
 [!CODE [concrt-allocators#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#3)]  
  
## Пример  
 Полный пример кода выглядит следующим образом.  
  
 [!CODE [concrt-allocators#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#4)]  
  
 На четырехпроцессорном компьютере этот пример создает следующие выходные данные.  
  
  **заняло 2031 мс с new\/delete.**  
**заняло 1672 мс с malloc\/free.**  
**заняло 656 мс с Alloc\/Free.** В этом примере тип, использующий функции `Alloc` и `Free`, обеспечивает наивысшую производительность памяти, так как функции `Alloc` и `Free` оптимизированы для частого выделения и освобождения блоков памяти из нескольких потоков.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `allocators.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc allocators.cpp**  
  
## См. также  
 [Функции управления памятью](../Topic/Memory%20Management%20Functions.md)   
 [Функция Alloc](../Topic/Alloc%20Function.md)   
 [Функция Free](../Topic/Free%20Function.md)