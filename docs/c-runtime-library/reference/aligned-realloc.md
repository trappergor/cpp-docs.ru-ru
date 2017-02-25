---
title: "_aligned_realloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_realloc"
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
  - "_aligned_realloc"
  - "aligned_realloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_realloc - функция"
  - "_aligned_realloc - функция"
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _aligned_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Синтаксис  
  
```  
void * _aligned_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment  
);  
```  
  
#### Параметры  
 \[входящий\] `memblock`  
 Текущий указатель на блок памяти.  
  
 \[входящий\] `size`  
 Размер запрошенного выделения памяти.  
  
 \[входящий\] `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
## Возвращаемое значение  
 `_aligned_realloc` возвращает void указатель перераспределенный \(и, возможно, перемещенный\) блок памяти.  Возвращаемое значение равно `NULL`, если размер равен нулю и аргумент буфера не равен `NULL`, или если доступной памяти недостаточно, чтобы развернуть блок заданного размера.  В первом случае исходный блок освобождается.  Во втором случае исходный блок не изменяется.  Возвращаемое значение указывает на дисковое пространство, которое гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от void, используйте приведение типа для возвращаемого значения.  
  
 Перераспределение памяти и изменение выравнивания блока является ошибкой.  
  
## Заметки  
 `_aligned_realloc` основан на `malloc`.  Дополнительные сведения об использовании `_aligned_offset_malloc` см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Эта функция устанавливает `errno` в значение `ENOMEM`, выделение памяти завершилось неудачно, или если запрошенный размер был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_realloc` проверяет свои параметры.  Если `alignment` не является степенью 2, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и устанавливает `errno` в значение `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_realloc`|\<malloc.h\>|  
  
## Пример  
 Дополнительные сведения см. в разделе [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)