---
title: "_aligned_offset_malloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7322f5a3fbf7bf3d9352181a68db17fad4bc9fcb
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc
Размещение памяти на указанной границе выравнивания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `size`  
 Размер запрошенного выделения памяти.  
  
 [входной] `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
 [входной] `offset`  
 Смещение в выделение памяти для принудительного выполнения выравнивания.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный блок памяти или значение `NULL` в случае сбоя операции.  
  
## <a name="remarks"></a>Примечания  
 `_aligned_offset_malloc` можно использовать в ситуациях, когда необходимо выравнивание вложенного элемента, например, если требуется выравнивание вложенного класса.  
  
 Функция `_aligned_offset_malloc` основана на функции `malloc`. Дополнительные сведения см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Функция `_aligned_offset_malloc` имеет метки `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если запрошенный размер был больше `_HEAP_MAXREQ`. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_offset_malloc` проверяет свои параметры. Если значение `alignment` не является степенью числа 2 или `offset` больше или равно `size` и не равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_offset_malloc`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
 Дополнительные сведения см. в разделе [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)
