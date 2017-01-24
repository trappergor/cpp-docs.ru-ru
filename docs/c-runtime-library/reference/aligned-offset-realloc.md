---
title: "_aligned_offset_realloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_realloc"
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
  - "aligned_offset_realloc"
  - "_aligned_offset_realloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "aligned_offset_realloc - функция"
  - "_aligned_offset_realloc - функция"
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Синтаксис  
  
```  
void * _aligned_offset_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### Параметры  
 `memblock`  
 Текущий указатель на блок памяти.  
  
 `size`  
 Размер выделяемой памяти.  
  
 `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
 `offset`  
 Смещение в выделении памяти для обеспечения выравнивания.  
  
## Возвращаемое значение  
 `_aligned_offset_realloc` возвращает void указатель на перераспределенный \(и, возможно, перемещенный\) блок памяти.  Возвращаемое значение равно `NULL`, если размер равен нулю и аргумент буфера не равен `NULL`, или если доступной памяти недостаточно, чтобы развернуть блок заданного размера.  В первом случае исходный блок освобождается.  Во втором случае исходный блок не изменяется.  Возвращаемое значение указывает на дисковое пространство, которое гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от void, используйте приведение типа для возвращаемого значения.  
  
 `_aligned_offset_realloc` помечена `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## Заметки  
 Подобно [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_realloc` позволяет, чтобы структура выравнивалась от смещения внутри структуры.  
  
 `_aligned_offset_realloc` основана на `malloc`.  Дополнительные сведения об использовании `_aligned_offset_malloc` см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  Если `memblock` равно `NULL`, функция вызывает `_aligned_offset_malloc` внутренне.  
  
 Эта функция устанавливает `errno` в значение `ENOMEM`, выделение памяти завершилось неудачно, или если запрошенный размер был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_offset_realloc` проверяет свои параметры.  Если `alignment` не степень двойки, или если `offset` больше или равно `size` и отлично от нуля, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и устанавливает `errno` в значение `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_offset_realloc`|\<malloc.h\>|  
  
## Пример  
 Дополнительные сведения см. в разделе [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)