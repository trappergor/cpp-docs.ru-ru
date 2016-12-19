---
title: "_aligned_offset_recalloc_dbg | Microsoft Docs"
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
  - "_aligned_offset_recalloc_dbg"
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
  - "aligned_offset_recalloc_dbg"
  - "_aligned_offset_recalloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_recalloc_dbg - функция"
  - "aligned_offset_recalloc_dbg - функция"
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_recalloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер блока памяти, который был выделен с помощью [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void * _aligned_offset_recalloc_dbg(    void *memblock,     size_t num,     size_t size,     size_t alignment,    size_t offset,    const char *filename,    int linenumber );  
```  
  
#### Параметры  
 \[входной\] `memblock`  
 Указатель текущего блока памяти.  
  
 \[входной\] `num`  
 Число элементов.  
  
 \[входной\] `size`  
 Длина каждого элемента в байтах.  
  
 \[входной\] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
 \[входной\] `offset`  
 Смещение в выделение памяти для принудительного выполнения выравнивания.  
  
 \[входной\] `filename`  
 Указатель на имя исходного файла, который запросил операцию `realloc`, или NULL.  
  
 \[входной\] `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция `realloc`, или NULL.  
  
## Возвращаемое значение  
 `_aligned_offset_recalloc_dbg` возвращает указатель void на перераспределенный \(и, возможно, перемещенный\) блок памяти.  Возвращаемое значение — `NULL`, если размер равен нулю и аргумент буфера не `NULL`, а также если недостаточно памяти для расширения блока до заданного размера.  В первом случае исходный блок освобождается.  Во втором случае исходный блок не изменяется.  Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа.  Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.  
  
## Заметки  
 `_aligned_offset_realloc_dbg` — это отладочная версия функции [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, каждый вызов функции `_aligned_offset_recalloc_dbg` сокращается до вызова функции \_`aligned_offset_recalloc`.  И \_`aligned_offset_recalloc`, и `_aligned_offset_recalloc_dbg` выполняют перераспределение блока памяти в основной куче, однако `_aligned_offset_recalloc_dbg` включает различные функции отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, а также сведения о `filename`\/`linenumber` для определения источника запросов на выделение.  
  
 `_aligned_offset_realloc_dbg` повторно выделяет указанный блок памяти, добавив немного больше пространства, чем запрошено `newSize`.  `newSize` может быть больше или меньше размера первоначально выделенного блока памяти.  Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи.  Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти.  Если блок памяти перемещен, содержимое исходного блока перезаписывается.  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти, а также если запрошенный размер \(`num` \* `size`\) был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_offset_recalloc_dbg` проверяет свои параметры.  Если значение `alignment` не является степенью числа 2 или `offset` больше или равно запрошенному размеру и не равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии основной кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Сведения о типах блоков выделения и о том, как они используются, см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h\>|  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)