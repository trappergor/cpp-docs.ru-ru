---
title: "_aligned_offset_realloc_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
caps.latest.revision: 8
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
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 01fb7ae608b710fca96b073e7b3ea0dcf07dbc53
ms.lasthandoff: 02/24/2017

---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg
Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_offset_realloc_dbg(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `memblock`  
 Указатель текущего блока памяти.  
  
 [входной] `size`  
 Размер выделения памяти.  
  
 [входной] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
 [входной] `offset`  
 Смещение в выделение памяти для принудительного выполнения выравнивания.  
  
 [входной] `filename`  
 Указатель на имя исходного файла, который запросил операцию `aligned_offset_realloc`, или NULL.  
  
 [входной] `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция `aligned_offset_realloc`, или NULL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_aligned_offset_realloc_dbg` возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение — `NULL`, если размер равен нулю и аргумент буфера не `NULL`, а также если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 `_aligned_offset_realloc_dbg` — это отладочная версия функции [_aligned_offset_realloc](../../c-runtime-library/reference/aligned-offset-realloc.md). Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, каждый вызов функции `_aligned_offset_realloc_dbg` сокращается до вызова функции _`aligned_offset_realloc`. И \_`aligned_offset_realloc`, и `_aligned_offset_realloc_dbg` выполняют перераспределение блока памяти в основной куче, однако `_aligned_offset_realloc_dbg` включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, а также сведения о `filename`/`linenumber` для определения источника запросов на выделение.  
  
 Как и [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_realloc_dbg` позволяет выполнить выравнивание структуры со смещением в пределах структуры.  
  
 `_realloc_dbg` повторно выделяет указанный блок памяти, добавив немного больше пространства, чем запрошено `newSize`. `newSize` может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Если блок памяти перемещен, содержимое исходного блока перезаписывается.  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если запрошенный размер был больше `_HEAP_MAXREQ`. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_offset_realloc_dbg` проверяет свои параметры. Если значение `alignment` не является степенью числа 2 или `offset` больше или равно `size` и не равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_offset_realloc_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
