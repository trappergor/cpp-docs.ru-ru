---
title: "_aligned_msize_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_msize_dbg"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_aligned_msize_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize_dbg"
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_msize_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает размер блока памяти, размещенного в куче \(только отладочная версия\).  
  
## Синтаксис  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### Параметры  
 \[входящий\] `memblock`  
 Указатель на блок памяти.  
  
 \[входящий\] `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
 \[входящий\] `offset`  
 Смещение в выделении памяти для обеспечения выравнивания.  
  
## Возвращаемое значение  
 Возвращает размер \(в байтах\) как целое число без знака.  
  
## Заметки  
 Значения `alignment` и `offset` должны совпадать со значениями, которые были переданы функции, выделившей блок.  
  
 `_aligned_msize_dbg` \- отладочная версия функции [\_aligned\_msize](../../c-runtime-library/reference/aligned-msize.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определена, каждый вызов `_aligned_msize_dbg` сводится к вызову `_aligned_msize`.  И `_aligned_msize`, и `_aligned_msize_dbg` вычисляют размер блока памяти в базовой куче, но `_aligned_msize_dbg` добавляет функциональность отладки: она включает буферы по обеим сторонам пользовательской части блоков памяти в возвращенном размере.  
  
 Эта функция проверяет свой параметр.  Если `memblock` указатель на null, или `alignment` \- не степень двойки, `_msize` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если ошибка обработана, то функция устанавливает `errno` в `EINVAL` и возвращает \-1.  
  
 Сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Дополнительные сведения о типах блока выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в отладочной сборке приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)