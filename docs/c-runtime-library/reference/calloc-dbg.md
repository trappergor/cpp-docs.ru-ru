---
title: "_calloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_calloc_dbg"
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
  - "_calloc_dbg"
  - "calloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_calloc_dbg - функция"
  - "calloc_dbg - функция"
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _calloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет несколько блоков памяти в куче с дополнительным пространством для отладочного заголовка и буферов перезаписи \(только для отладочной версии\).  
  
## Синтаксис  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Параметры  
 `num`  
 Запрошенное число блоков памяти.  
  
 `size`  
 Запрошенный размер каждого блока памяти \(в байтах\).  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 Дополнительные сведения о типах блока выделения и способах их использования см. в разделе[Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
 `filename`  
 Указатель на имя файла исходного кода, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер линии в исходном файле, где была запрошена операция выделения, или `NULL`.  
  
 Параметры `filename` и `linenumber` доступны, только если `_calloc_dbg` был вызван явным образом или определена константа препроцессора [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md).  
  
## Возвращаемое значение  
 В случае успешного завершения эта функция либо возвращает указатель на пользовательскую часть последнего выделенного блока памяти, вызывает новую функцию обработчика, или возвращает значение `NULL`.  Полное описание поведения возврата см. в разделе Заметки ниже.  Дополнительные сведения о том, как используется новая функция обработчика, см. в разделе [calloc](../../c-runtime-library/reference/calloc.md).  
  
## Заметки  
 `_calloc_dbg` \- отладочная версия функции [calloc](../../c-runtime-library/reference/calloc.md).  Если [\_DEBUG](../Topic/_DEBUG.md) не определена, каждый вызов `_calloc_dbg` сводится к вызову `calloc`.  И `calloc`, и `_calloc_dbg` выделяют `num` блоков памяти в базовой куче, но `_calloc_dbg` предоставляет несколько функций для отладки:  
  
-   Буферы по обеим сторонам участка пользовательской части для проверки на утечки.  
  
-   Параметр типа блоков для отслеживания определенных типов выделения.  
  
-   `filename`\/`linenumber` сведения для определения места запросов на выделение.  
  
 `_calloc_dbg` выделяет каждый блок памяти с немного большим пространством, чем требовал `size`.  Дополнительное место используется диспетчером отладочной кучи для связывания отладочных блоков памяти и обеспечения приложения сведениями заголовка отладки и буферами перезаписи.  При выделении блока, пользовательская часть блока заполняется значением 0xCD, а каждый из буферов перезаписи заполняется 0xFD.  
  
 `_calloc_dbg` устанавливает `errno` в `ENOMEM`, если не удается выделить память; возвращает `EINVAL`, если требуемый объем памяти \(включая ранее упомянутую нагрузку\) превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Сведения о том, как происходит выделение, инициализация и управление блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в отладочной сборке приложения см. в разделе [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_calloc_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
  **Allocated memory successfully**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [\_DEBUG](../Topic/_DEBUG.md)