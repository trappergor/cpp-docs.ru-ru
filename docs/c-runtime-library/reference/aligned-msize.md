---
title: "_aligned_msize | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
dev_langs:
- C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 6
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
ms.openlocfilehash: ac7ad08c7040ca317ef9e9a95acab6a8df3a7eed
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="alignedmsize"></a>_aligned_msize
Возвращает размер блока памяти, выделенного в куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t _msize(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `memblock`  
 Указатель на блок памяти.  
  
 [in] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
 [входной] `offset`  
 Смещение в выделение памяти для принудительного выполнения выравнивания.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер (в байтах) как целое число без знака.  
  
## <a name="remarks"></a>Примечания  
 Функция `_aligned_msize` возвращает размер блока памяти, выделенного вызовом функции [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md) (байт). Значения `alignment` и `offset` должны совпадать со значениями, которые были переданы функции, выделившей блок.  
  
 Когда приложение связано с отладочной версией библиотек среды выполнения языка C, функция `_aligned_msize` соответствует функции [_aligned_msize_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Эта функция проверяет свои параметры. Если `memblock` является указателем NULL или `alignment` не является степенью двойки, функция `_msize` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка обработана, функция задает для параметра `errno` значение `EINVAL` и возвращает –1.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)
