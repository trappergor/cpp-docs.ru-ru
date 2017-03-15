---
title: "_realloc_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
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
ms.openlocfilehash: 80dade4b6e288e80e37c7354fe73d4776227f401
ms.lasthandoff: 02/24/2017

---
# <a name="reallocdbg"></a>_realloc_dbg
Перераспределяет указанный блок памяти в куче, перемещая его и (или) изменяя его размер (только для отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `userData`  
 Указатель на ранее выделенный блок памяти.  
  
 `newSize`  
 Запрошенный размер повторно выделенного блока (в байтах).  
  
 `blockType`  
 Запрошенный тип повторно выделенного блока (в байтах): `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию `realloc`, или NULL.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция `realloc`, или NULL.  
  
 Параметры `filename` и `linenumber` доступны, только если функция `_realloc_dbg` была явно вызвана или была определена константа препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении эта функция возвращает указатель на пользовательскую часть перераспределенного блока памяти, вызывает новую функцию обработчика или возвращает значение NULL. Полное описание поведения возвращения см. в следующем разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="remarks"></a>Примечания  
 `_realloc_dbg` — это отладочная версия функции [realloc](../../c-runtime-library/reference/realloc.md). Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов функции `_realloc_dbg` сокращается до вызова функции `realloc`. И `realloc`, и `_realloc_dbg` выполняют перераспределение блока памяти в основной куче, однако `_realloc_dbg` включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, а также сведения о `filename`/`linenumber` для определения источника запросов на выделение.  
  
 `_realloc_dbg` повторно выделяет указанный блок памяти, добавив немного больше пространства, чем запрошено `newSize`. `newSize` может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Если блок памяти перемещен, содержимое исходного блока перезаписывается.  
  
 `_realloc_dbg` задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_realloc_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)
