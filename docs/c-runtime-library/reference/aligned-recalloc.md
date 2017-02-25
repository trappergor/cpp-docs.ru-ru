---
title: "_aligned_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_recalloc"
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
  - "aligned_recalloc"
  - "_aligned_recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_recalloc - функция"
  - "_aligned_recalloc - функция"
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер блока памяти, выделенного с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) и инициализирует память нулями.  
  
## Синтаксис  
  
```  
void * _aligned_recalloc(  
   void *memblock,   
   size_t num,  
   size_t size,   
   size_t alignment  
);  
```  
  
#### Параметры  
 \[входящий\] `memblock`  
 Текущий указатель на блок памяти.  
  
 \[входящий\] `num`  
 Количество элементов.  
  
 \[входящий\] `size`  
 Размер в байтах каждого элемента.  
  
 \[входящий\] `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
## Возвращаемое значение  
 `_aligned_recalloc` возвращает void указатель перераспределенный \(и, возможно, перемещенный\) блок памяти.  Возвращаемое значение равно `NULL`, если размер равен нулю и аргумент буфера не равен `NULL`, или если доступной памяти недостаточно, чтобы развернуть блок заданного размера.  В первом случае исходный блок освобождается.  Во втором случае исходный блок не изменяется.  Возвращаемое значение указывает на дисковое пространство, которое гарантированно выравнено подходящим для хранения любого типа объекта образом.  Чтобы получить указатель на тип, отличный от void, используйте приведение типа для возвращаемого значения.  
  
 Перераспределение памяти и изменение выравнивания блока является ошибкой.  
  
## Заметки  
 `_aligned_recalloc` основана на `malloc`.  Дополнительные сведения об использовании `_aligned_offset_malloc` см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Эта функция устанавливает `errno` в значение `ENOMEM`, выделение памяти завершилось неудачно, или если запрошенный размер был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_recalloc` проверяет свои параметры.  Если `alignment` не является степенью 2, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и устанавливает `errno` в значение `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_recalloc`|\<malloc.h\>|  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)   
 [\_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)