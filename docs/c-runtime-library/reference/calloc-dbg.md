---
title: "_calloc_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _calloc_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _calloc_dbg
- calloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f505aa045dcee661bfddec2ed1d01a7b77efcc51
ms.lasthandoff: 02/24/2017

---
# <a name="callocdbg"></a>_calloc_dbg
Выделяет ряд блоков памяти в куче с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `num`  
 Запрошенное число блоков памяти.  
  
 `size`  
 Запрошенный размер каждого блока памяти (байт).  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 Дополнительные сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
 Параметры `filename` и `linenumber` доступны, только если функция `_calloc_dbg` была явно вызвана или была определена константа препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении эта функция возвращает указатель на пользовательскую часть выделенного блока памяти, вызывает новую функцию обработчика или возвращает значение `NULL`. Полное описание поведения возвращения см. в разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [calloc](../../c-runtime-library/reference/calloc.md).  
  
## <a name="remarks"></a>Примечания  
 `_calloc_dbg` — это отладочная версия функции [calloc](../../c-runtime-library/reference/calloc.md). Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, каждый вызов функции `_calloc_dbg` сокращается до вызова функции `calloc`. Обе функции, `calloc` и `_calloc_dbg`, выделяют блоки памяти `num` в основной куче, но `_calloc_dbg` предлагает несколько функций отладки:  
  
-   Буферы с обеих сторон пользовательской части блока, которые необходимо проверить на наличие утечек.  
  
-   Параметр типа блока для отслеживания конкретных типов выделения.  
  
-   Данные `filename`/`linenumber`, определяющие источник запросов на выделение памяти.  
  
 `_calloc_dbg` выделяет каждый блок памяти, добавляя немного больше пространства, чем запрошено `size`. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.  
  
 `_calloc_dbg` задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти; значение `EINVAL` возвращается, если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_calloc_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Allocated memory successfully  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
