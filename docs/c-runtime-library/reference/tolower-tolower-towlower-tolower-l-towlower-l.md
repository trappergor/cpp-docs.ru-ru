---
title: "tolower, _tolower, towlower, _tolower_l, _towlower_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs:
- C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e9387288db68a2af4897daece878f6cec1e522ac
ms.lasthandoff: 02/24/2017

---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l
Преобразует символ в строчный.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `c`  
 Символ для преобразования.  
  
 [in] `locale`  
 Языковой стандарт для перевода в определенном языковом стандарте.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм преобразует копию `c` в строчный символ, если это преобразование возможно, и возвращает результат. Возвращаемое значение для указания ошибки не зарезервировано.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих подпрограмм преобразует указанную прописную букву в строчную, если это возможно и уместно. Преобразование регистра `towlower` зависит от языкового стандарта. Изменяются только символы, соответствующие текущему языковому стандарту. Функции без суффикса `_l` используют текущий языковой стандарт. Версии этих функций, имеющие суффикс `_l`, идентичны функциям без суффикса, за исключением того, что они принимают языковой стандарт в качестве параметра и используют его вместо текущего языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Чтобы функция `_tolower` давала ожидаемые результаты, обе функции [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) и [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) должны возвращать ненулевое значение.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
> Функции  `_tolower_l` и `_towlower_l` не зависят от языкового стандарта и не предназначены для непосредственного вызова. Они предназначены для внутреннего использования `_totlower_l`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`tolower`|\<ctype.h>|  
|`_tolower`|\<ctype.h>|  
|`towlower`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции to](../../c-runtime-library/to-functions.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::Char::ToLower](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Функции to](../../c-runtime-library/to-functions.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
