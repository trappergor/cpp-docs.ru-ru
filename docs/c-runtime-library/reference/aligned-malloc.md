---
title: "_aligned_malloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_malloc
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
- _aligned_malloc
- alligned_malloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_malloc function
- _aligned_malloc function
ms.assetid: fb788d40-ee94-4039-aa4d-97d73dab1ca0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 465321a36ee1a76fe9ebe507fb99a32c27785809
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="alignedmalloc"></a>_aligned_malloc
Размещение памяти на указанной границе выравнивания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void * _aligned_malloc(  
    size_t size,   
    size_t alignment  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `size`  
 Размер запрошенного размещения памяти.  
  
 `alignment`  
 Значение выравнивания, которое должно быть целой степенью числа 2.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный блок памяти или значение `NULL` в случае сбоя операции. Указатель делится на `alignment`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_aligned_malloc` основана на функции [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Функция `_aligned_malloc` имеет метки `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
 Эта функция задает для `errno` значение `ENOMEM` в случае сбоя выделения памяти или если запрошенный размер был больше `_HEAP_MAXREQ`. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, `_aligned_malloc` проверяет свои параметры. Если `alignment` не является степенью числа 2 или `size` равен нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `NULL` и задает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_malloc`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
  
```  
// crt_aligned_malloc.c  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main() {  
    void    *ptr;  
    size_t  alignment,  
            off_set;  
  
    // Note alignment should be 2^N where N is any positive int.  
    alignment = 16;  
    off_set = 5;  
  
    // Using _aligned_malloc  
    ptr = _aligned_malloc(100, alignment);  
    if (ptr == NULL)  
    {  
        printf_s( "Error allocation aligned memory.");  
        return -1;  
    }  
    if (((unsigned long long)ptr % alignment ) == 0)  
        printf_s( "This pointer, %p, is aligned on %zu\n",  
                  ptr, alignment);  
    else  
        printf_s( "This pointer, %p, is not aligned on %zu\n",   
                  ptr, alignment);  
  
    // Using _aligned_realloc  
    ptr = _aligned_realloc(ptr, 200, alignment);  
    if ( ((unsigned long long)ptr % alignment ) == 0)  
        printf_s( "This pointer, %p, is aligned on %zu\n",  
                  ptr, alignment);  
    else  
        printf_s( "This pointer, %p, is not aligned on %zu\n",   
                  ptr, alignment);  
    _aligned_free(ptr);  
  
    // Using _aligned_offset_malloc  
    ptr = _aligned_offset_malloc(200, alignment, off_set);  
    if (ptr == NULL)  
    {  
        printf_s( "Error allocation aligned offset memory.");  
        return -1;  
    }  
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)  
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",  
                  ptr, off_set, alignment);  
    else  
        printf_s( "This pointer, %p, does not satisfy offset %zu "  
                  "and alignment %zu\n",ptr, off_set, alignment);  
  
    // Using _aligned_offset_realloc  
    ptr = _aligned_offset_realloc(ptr, 200, alignment, off_set);  
    if (ptr == NULL)  
    {  
        printf_s( "Error reallocation aligned offset memory.");  
        return -1;  
    }  
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)  
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",  
                  ptr, off_set, alignment);  
    else  
        printf_s( "This pointer, %p, does not satisfy offset %zu and "  
                  "alignment %zu\n", ptr, off_set, alignment);  
  
    // Note that _aligned_free works for both _aligned_malloc  
    // and _aligned_offset_malloc. Using free is illegal.  
    _aligned_free(ptr);  
}  
```  
  
```Output  
This pointer, 3280880, is aligned on 16  
This pointer, 3280880, is aligned on 16  
This pointer, 3280891, is offset by 5 on alignment of 16  
This pointer, 3280891, is offset by 5 on alignment of 16  
```  
  
## <a name="see-also"></a>См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)