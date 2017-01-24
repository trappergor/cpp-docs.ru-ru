---
title: "Выравнивание данных | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data.alignment"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "выравнивание данных [C++]"
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Выравнивание данных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие функции библиотеки времени выполнения языка C поддерживают выравнивание данных.  
  
### Процедуры выравнивания данных  
  
|Подпрограмма|Применение|Эквивалент в .NET Framework|  
|------------------|----------------|---------------------------------|  
|[\_aligned\_free](../c-runtime-library/reference/aligned-free.md)|Освобождает блок памяти, выделенной с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_free\_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Освобождает блок памяти, выделенной с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(только отладка\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)|Выделяет память по определенной границе выравнивания.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc\_dbg](../Topic/_aligned_malloc_dbg.md)|Выделяет память по определенной границе выравнивания с дополнительным пробелом для отладочного заголовка и перезаписывает буферы \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize](../c-runtime-library/reference/aligned-msize.md)|Возвращает размер блока памяти, размещенного в куче.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize\_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Возвращает размер блока памяти, размещенного в куче \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Выделяет память по определенной границе выравнивания.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc\_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Выделяет память по определенной границе выравнивания \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc\_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) и инициализирует память нулями.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc\_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) и инициализирует память нулями \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc](../c-runtime-library/reference/aligned-realloc.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc\_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) и инициализирует память нулями.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc\_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) и инициализирует память нулями \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)