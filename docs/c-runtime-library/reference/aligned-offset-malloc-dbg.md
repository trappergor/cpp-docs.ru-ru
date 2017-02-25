---
title: "_aligned_offset_malloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_malloc_dbg"
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
  - "_aligned_offset_malloc_dbg"
  - "aligned_offset_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_malloc_dbg - функция"
  - "aligned_offset_malloc_dbg - функция"
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_offset_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет память по определенной границе выравнивания \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Параметры  
 \[входящий\] `size`  
 Размер запрошенного выделения памяти.  
  
 \[входящий\] `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
 \[входящий\] `offset`  
 Смещение в выделении памяти для обеспечения выравнивания.  
  
 \[входящий\] `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или NULL.  
  
 \[входящий\] `linenumber`  
 Номер строки в исходном файле, где была запрошена операция выделения, или NULL.  
  
## Возвращаемое значение  
 Указатель на блок памяти, который был выделен, или `NULL` , если операция завершилась неудачно.  
  
## Заметки  
 `_aligned_offset_malloc_dbg` \- отладочная версия функции [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определена, каждый вызов `_aligned_offset_malloc_dbg` сводится к вызову `_aligned_offset_malloc`.  И `_aligned_offset_malloc`, и `_aligned_offset_malloc_dbg` выделяют блок памяти в базовой куче, но `_aligned_offset_malloc_dbg` предлагает несколько функций отладки: буферы по обеим сторонам пользовательского участка блока для проверки на наличие утечек, параметр типа блока для отслеживания определенных типов выделения и сведения по `filename`\/`linenumber` для определения источника запросов на выделение.  
  
 `_aligned_offset_malloc_dbg` выделяет блок памяти с немного большим пространством, чем требовал `size`.  Дополнительное место используется диспетчером отладочной кучи для связывания отладочных блоков памяти и обеспечения приложения сведениями заголовка отладки и буферами перезаписи.  При выделении блока, пользовательская часть блока заполняется значением 0xCD, а каждый из буферов перезаписи заполняется 0xFD.  
  
 `_aligned_offset_malloc_dbg` удобна, когда выравнивание необходимо во вложенном элементе; например, если выравнивание было необходимо во вложенном классе.  
  
 `_aligned_offset_malloc_dbg` основана на `malloc`; дополнительные сведения см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Эта функция устанавливает `errno` в значение `ENOMEM`, выделение памяти завершилось неудачно, или если запрошенный размер был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_offset_malloc` проверяет свои параметры.  Если `alignment` не степень двойки, или если `offset` больше или равно `size` и отлично от нуля, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и устанавливает `errno` в значение `EINVAL`.  
  
 Сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Дополнительные сведения о типах блока выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)