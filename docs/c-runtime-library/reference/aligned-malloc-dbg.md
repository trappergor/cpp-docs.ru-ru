---
title: "_aligned_malloc_dbg | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: dd7cba44a8352afdf052e570de09499918594e26
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="alignedmallocdbg"></a>_aligned_malloc_dbg
Выделяет память в указанных границах выравнивания с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_malloc_dbg(  
    size_t size,   
    size_t alignment,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `size`  
 Размер запрошенного выделения памяти.  
  
 [входной] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
 [входной] `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или NULL.  
  
 [входной] `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или NULL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный блок памяти или значение `NULL` в случае сбоя операции.  
  
## <a name="remarks"></a>Примечания  
 `_aligned_malloc_dbg` — это отладочная версия функции [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md). Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, каждый вызов функции `_aligned_malloc_dbg` сокращается до вызова функции `_aligned_malloc`. И `_aligned_malloc`, и `_aligned_malloc_dbg` выполняют выделение блока памяти в основной куче, однако `_aligned_malloc_dbg` включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек и сведения о `filename`/`linenumber` для определения источника запросов на выделение.  
  
 `_aligned_malloc_dbg` выделяет блок памяти, добавив немного больше пространства, чем запрошено `size`. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.  
  
 `_aligned_malloc_dbg` задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_malloc_dbg` проверяет свои параметры. Если `alignment` не является степенью числа 2 или `size` равен нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_malloc_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
