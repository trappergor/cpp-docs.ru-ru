---
title: "_malloc_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2bdbd0b6bc0a9af533aa41b5d29a171bb56ac382
ms.lasthandoff: 02/24/2017

---
# <a name="mallocdbg"></a>_malloc_dbg
Выделяет блок памяти в куче с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_malloc_dbg(  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `size`  
 Запрошенный размер блока памяти (байт).  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или NULL.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или NULL.  
  
 Параметры `filename` и `linenumber` доступны, только если функция `_malloc_dbg` была явно вызвана или была определена константа препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении эта функция возвращает указатель на пользовательскую часть выделенного блока памяти, вызывает новую функцию обработчика или возвращает значение NULL. Полное описание поведения возвращения см. в следующем разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [malloc](../../c-runtime-library/reference/malloc.md).  
  
## <a name="remarks"></a>Примечания  
 `_malloc_dbg` — это отладочная версия функции [malloc](../../c-runtime-library/reference/malloc.md). Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов функции `_malloc_dbg` сокращается до вызова функции `malloc`. И `malloc`, и `_malloc_dbg` выполняют выделение блока памяти в основной куче, однако `_malloc_dbg` включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, а также сведения о `filename`/`linenumber` для определения источника запросов на выделение.  
  
 `_malloc_dbg` выделяет блок памяти, добавив немного больше пространства, чем запрошено `size`. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.  
  
 `_malloc_dbg` задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_malloc_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования `_malloc_dbg` см. в описании [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)
