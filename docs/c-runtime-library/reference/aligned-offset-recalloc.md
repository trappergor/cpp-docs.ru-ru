---
title: "_aligned_offset_recalloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c2586cdd836795a31e457edcba42292a6901ec6f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc
Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель текущего блока памяти.  
  
 `num`  
 Число элементов.  
  
 `size`  
 Длина каждого элемента в байтах.  
  
 `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью числа 2.  
  
 `offset`  
 Смещение в выделение памяти для принудительного выполнения выравнивания.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_aligned_offset_recalloc` возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение — `NULL`, если размер равен нулю и аргумент буфера не `NULL`, а также если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.  
  
 Функция `_aligned_offset_recalloc` имеет метки `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## <a name="remarks"></a>Примечания  
 Как и [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_recalloc` позволяет выполнить выравнивание структуры со смещением в пределах структуры.  
  
 Функция `_aligned_offset_recalloc` основана на функции `malloc`. Дополнительные сведения об использовании `_aligned_offset_malloc` см. в разделе [malloc](../../c-runtime-library/reference/malloc.md). Если функция `memblock` имеет значение `NULL`, она вызывает `_aligned_offset_malloc` внутри системы.  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти, а также если запрошенный размер (`num` * `size`) был больше `_HEAP_MAXREQ`. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_offset_recalloc` проверяет свои параметры. Если значение `alignment` не является степенью числа 2 или `offset` больше или равно запрошенному размеру и не равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_offset_recalloc`|\<malloc.h>|  
  
## <a name="see-also"></a>См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)
