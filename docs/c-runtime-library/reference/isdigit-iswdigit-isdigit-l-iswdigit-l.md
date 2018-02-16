---
title: "isdigit, iswdigit, _isdigit_l, _iswdigit_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isdigit_l
- iswdigit
- _iswdigit_l
- isdigit
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
- _iswdigit_l
- _isdigit_l
- iswdigit
- isdigit
- _istdigit
- _istdigit_l
dev_langs:
- C++
helpviewer_keywords:
- iswdigit function
- iswdigit_l function
- _iswdigit_l function
- _istdigit_l function
- _istdigit function
- istdigit function
- isdigit function
- isdigit_l function
- _ismbcdigit_l function
- _isdigit_l function
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 004186bc7ea74cb6ab2c39d25a9b3d3efeb556fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="isdigit-iswdigit-isdigitl-iswdigitl"></a>isdigit, iswdigit, _isdigit_l, _iswdigit_l
Определяет, представляет ли целое число символ десятичной цифры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int isdigit(   
   int c   
);  
int iswdigit(   
   wint_t c   
);  
int _isdigit_l(   
   int c,  
   _locale_t locale  
);  
int _iswdigit_l(   
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемое целое число.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм возвращает отличное от нуля значение, если `c` — конкретное представление символа десятичной цифры. `isdigit` возвращает ненулевое значение, если `c` является десятичной цифрой (0 - 9). Функция `iswdigit` возвращает ненулевое значение, если `c` представляет собой расширенный символ, соответствующий символу десятичной цифры. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию.  
  
 Версии этих функций с суффиксом `_l` используют переданный параметр языкового стандарта вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Поведение функций `isdigit` и `_isdigit_l` не определено, если `c` не является концом файла или не находится в диапазоне от 0 по 0xFF включительно. Если используется библиотека отладки CRT и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istdigit`|`isdigit`|[_ismbcdigit](../../c-runtime-library/reference/ismbcalnum-functions.md)|`iswdigit`|  
|`_istdigit_l`|`_isdigit_l`|[_ismbcdigit_l](../../c-runtime-library/reference/ismbcalnum-functions.md)|`_iswdigit_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`isdigit`|\<ctype.h>|  
|`iswdigit`|\<ctype.h> или \<wchar.h>|  
|`_isdigit_l`|\<ctype.h>|  
|`_iswdigit_l`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)