---
title: "_aligned_msize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_msize"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_aligned_msize"
  - "aligned_msize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize - функция"
  - "aligned_msize - функция"
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _aligned_msize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает размер блока памяти, размещенного в куче.  
  
## Синтаксис  
  
```  
size_t _msize(  
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
 Функция `_aligned_msize` возвращает размер \(в байтах\) блока памяти, выделенного вызовом [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_realloc](../../c-runtime-library/reference/aligned-realloc.md).  Значения `alignment` и `offset` должны совпадать со значениями, которые были переданы функции, выделившей блок.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, `_aligned_msize` соответствует [\_aligned\_msize\_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Отладочная куча CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Эта функция проверяет свой параметр.  Если `memblock` указатель на null, или `alignment` \- не степень двойки, `_msize` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если ошибка обработана, то функция устанавливает `errno` в `EINVAL` и возвращает \-1.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_msize`|\<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)