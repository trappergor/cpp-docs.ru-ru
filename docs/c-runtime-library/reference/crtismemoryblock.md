---
title: "_CrtIsMemoryBlock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsMemoryBlock"
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
  - "CrtlsMemoryBlock"
  - "_CrtIsMemoryBlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtIsMemoryBlock - функция"
  - "CrtIsMemoryBlock - функция"
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _CrtIsMemoryBlock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, что указанный блок памяти находится в локальной куче и что он имеет допустимый идентификатор типа блоков отладочной кучи \(только отладочная версия\).  
  
## Синтаксис  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### Параметры  
 \[входящий\] `userData`  
 Указатель на начало блока памяти, который требуется проверить.  
  
 \[входящий\] `size`  
 Размер указанного блока \(в байтах\).  
  
 \[исходящий\] `requestNumber`  
 Указатель на номер выделения блока или `NULL`.  
  
 \[исходящий\] `filename`  
 Указатель на имя исходного файла, который запросил блок или `NULL`.  
  
 \[исходящий\] `linenumber`  
 Указатель на номер строки в файле исходного кода или `NULL`.  
  
## Возвращаемое значение  
 `_CrtIsMemoryBlock` возвращает `TRUE` , если указанный блок памяти находится в локальной куче имеет допустимый идентификатор типа блоков памяти отладочной кучи; в противном случае функция возвращает `FALSE`.  
  
## Заметки  
 Функция `_CrtIsMemoryBlock` проверяет, находится ли указанный блок памяти в локальной куче приложения и имеет ли он допустимый идентификатор типа блоков.  Эту функцию также можно использовать для получения порядкового номера выделения объекта и имени файла исходного кода\/номера строки, в котором было первоначально запрошено выделение блоков памяти.  Если для параметров `requestNumber`, `filename` или `linenumber` передаются отличные от NULL значения, `_CrtIsMemoryBlock` задает этим параметрам значения в заголовке отладки блока памяти, если этот блок находится в локальной куче.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtIsMemoryBlock` удаляются во время предварительной обработки.  
  
 Если `_CrtIsMemoryBlock` завершается ошибкой, возвращается `FALSE` и выходным параметрам присваиваются значения по умолчанию: 0 для `requestNumber` и `lineNumber` и `NULL` для `filename`.  
  
 Поскольку эта функция возвращает `TRUE` или `FALSE`, она может быть передана одному из макросов [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) для создания простого отладочного механизма обработки ошибок.  Следующий пример вызывает сбой проверочного утверждения, если адрес не находится в локальной куче:  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Дополнительные сведения о том, как можно использовать `_CrtIsMemoryBlock` с другими отладочными функциями и макросами, см. в разделе [Макросы для создания отчетов](../Topic/Macros%20for%20Reporting.md).  Сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Пример см. в разделе [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)