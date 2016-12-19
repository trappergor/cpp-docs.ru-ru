---
title: "_malloc_dbg | Microsoft Docs"
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
  - "_malloc_dbg"
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
  - "malloc_dbg"
  - "_malloc_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_malloc_dbg - функция"
  - "malloc_dbg - функция"
  - "выделение памяти"
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет блок памяти в куче с дополнительным пространством для заголовка отладки и буферов перезаписи \(только отладочная версия\).  
  
## Синтаксис  
  
```  
void *_malloc_dbg(    size_t size,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Параметры  
 `size`  
 Запрошенный размер блока памяти \(байт\).  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или NULL.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или NULL.  
  
 Параметры `filename` и `linenumber` доступны, только если функция `_malloc_dbg` была явно вызвана или была определена константа препроцессора [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md).  
  
## Возвращаемое значение  
 При успешном выполнении эта функция возвращает указатель на пользовательскую часть выделенного блока памяти, вызывает новую функцию обработчика или возвращает значение NULL.  Полное описание поведения возвращения см. в следующем разделе "Примечания".  Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [malloc](../../c-runtime-library/reference/malloc.md).  
  
## Заметки  
 `_malloc_dbg` — это отладочная версия функции [malloc](../../c-runtime-library/reference/malloc.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, каждый вызов функции `_malloc_dbg` сокращается до вызова функции `malloc`.  И `malloc`, и `_malloc_dbg` выполняют выделение блока памяти в основной куче, однако `_malloc_dbg` включает различные функции отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, а также сведения о `filename`\/`linenumber` для определения источника запросов на выделение.  
  
 `_malloc_dbg` выделяет блок памяти, добавив немного больше пространства, чем запрошено `size`.  Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи.  При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.  
  
 `_malloc_dbg` задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если необходимый объем памяти \(включая ранее упомянутую нагрузку\) превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии основной кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Сведения о типах блоков выделения и о том, как они используются, см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_malloc_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Пример использования `_malloc_dbg` см. в описании [crt\_dbg1](http://msdn.microsoft.com/ru-ru/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)