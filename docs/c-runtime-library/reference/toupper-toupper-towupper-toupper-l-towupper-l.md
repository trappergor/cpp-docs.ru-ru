---
title: "toupper, _toupper, towupper, _toupper_l, _towupper_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
dev_langs:
- C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2da016750a125c6645a878b3fee04a09c3e76e26
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l
Преобразуют символ в верхний регистр.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ для преобразования.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм преобразует копию `c`, если это преобразование возможно, и возвращает результат.  
  
 Если `c` является расширенным символом, для которого `iswlower` имеет ненулевое значение, и существует соответствующий расширенный символ, для которого `iswupper` имеет ненулевое значение, то `towupper` возвращает соответствующий расширенный символ; в противном случае `towupper` возвращает `c` без изменений.  
  
 Возвращаемое значение для указания ошибки не зарезервировано.  
  
 Чтобы функция `toupper` давала ожидаемые результаты, обе функции [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) и [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) должны возвращать ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих подпрограмм преобразует указанную строчную букву в прописную, если это возможно и уместно. Преобразование регистра `towupper` зависит от языкового стандарта. Изменяются только символы, соответствующие текущему языковому стандарту. Функции без суффикса `_l` используют текущий языковой стандарт. Версии этих функций с суффиксом `_l` идентичны функциям без суффикса, за исключением того, что они принимают языковой стандарт в качестве параметра и используют его вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Чтобы функция `toupper` давала ожидаемые результаты, обе функции [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) и [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) должны возвращать ненулевое значение.  
  
 [Процедуры преобразования данных](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  Функции `_toupper_l` и `_towupper_l` не зависят от языкового стандарта и не предназначены для непосредственного вызова. Они предназначены для внутреннего использования `_totupper_l`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`toupper`|\<ctype.h>|  
|`_toupper`|\<ctype.h>|  
|`towupper`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции to](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Функции to](../../c-runtime-library/to-functions.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)