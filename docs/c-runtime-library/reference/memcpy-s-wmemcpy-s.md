---
title: "memcpy_s, wmemcpy_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy_s
- wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 44d9ecb713c0fa85f11c3d01b5a15707b0bfaf57
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s
Копирует байты между буферами. Это версии функций [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dest`  
 Новый буфер.  
  
 `destSize`  
 Размер буфера назначения в байтах для функции memcpy_s и в расширенных символах (wchar_t) для wmemcpy_s.  
  
 `src`  
 Буфер, из которого происходит копирование.  
  
 `count`  
 Число копируемых символов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`dest`|`destSize`|`src`|`count`|Возвращаемое значение|Содержимое `dest`|  
|------------|----------------|-----------|---|------------------|------------------------|  
|any|любые|любые|0|0|Без изменений|  
|`NULL`|любые|любые|ненулевое значение|`EINVAL`|Без изменений|  
|любые|любые|`NULL`|ненулевое значение|`EINVAL`|`dest` обнуляется|  
|любые|< `count`|любые|ненулевое значение|`ERANGE`|`dest` обнуляется|  
  
## <a name="remarks"></a>Примечания  
 `memcpy_s` копирует `count` байт из `src` в `dest`; `wmemcpy_s` копирует `count` расширенных символов (двухбайтовых). При перекрытии исходного и конечного буферов поведение `memcpy_s` не определено. Используйте `memmove_s` для обработки перекрывающихся областей.  
  
 Эти функции проверяют свои параметры. Если параметр `count` имеет ненулевое значение и `dest` или `src` является указателем NULL, либо если `destSize` меньше `count`, эти функции вызывают обработчик недопустимого параметра, как указано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции возвращают `EINVAL` или `ERANGE` и присваивают параметру `errno` возвращаемое значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`memcpy_s`|\<memory.h> или \<string.h>|  
|`wmemcpy_s`|\<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## <a name="see-also"></a>См. также  
 [Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)
