---
title: "_aligned_realloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_realloc
- aligned_realloc
dev_langs: C++
helpviewer_keywords:
- aligned_realloc function
- _aligned_realloc function
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 293e519cd107ef64d81d59f08cf7f8d4871e8e6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="alignedrealloc"></a>_aligned_realloc
Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `memblock`  
 Указатель текущего блока памяти.  
  
 [входной] `size`  
 Размер запрошенного выделения памяти.  
  
 [входной] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_aligned_realloc` возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение — `NULL`, если размер равен нулю и аргумент буфера не `NULL`, а также если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.  
  
 Будет ошибкой повторно выделить память и изменить выравнивание блока.  
  
## <a name="remarks"></a>Примечания  
 Функция `_aligned_realloc` основана на функции `malloc`. Дополнительные сведения об использовании `_aligned_offset_malloc` см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если запрошенный размер был больше `_HEAP_MAXREQ`. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_realloc` проверяет свои параметры. Если `alignment` не является степенью числа 2, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_realloc`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
 Дополнительные сведения см. в разделе [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)