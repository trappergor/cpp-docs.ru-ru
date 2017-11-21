---
title: "isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _iswxdigit_l
- iswxdigit
- isxdigit
- _isxdigit_l
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
- iswxdigit
- isxdigit
- _istxdigit
dev_langs: C++
helpviewer_keywords:
- isxdigit function
- istxdigit function
- _iswxdigit_l function
- _istxdigit function
- _isxdigit_l function
- iswxdigit_l function
- isxdigit_l function
- hexadecimal characters
- iswxdigit function
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 363a1b30e410bbb13a9101c268d48a2cb6ff1787
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="isxdigit-iswxdigit-isxdigitl-iswxdigitl"></a>isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l
Определяет, представляет ли целое число шестнадцатеричный символ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int isxdigit(  
   int c   
);  
int iswxdigit(  
   wint_t c   
);  
int _isxdigit_l(  
   int c,  
   _locale_t locale  
);  
int _iswxdigit_l(  
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
 Каждая из этих подпрограмм возвращает отличное от нуля значение, если `c` — конкретное представление шестнадцатеричного символа. `isxdigit`возвращает ненулевое значение, если `c` представляет собой шестнадцатеричную цифру (A - F, a - f или 0 - 9). Функция `iswxdigit` возвращает ненулевое значение, если `c` представляет собой расширенный символ, соответствующий шестнадцатеричному символу. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию.  
  
 Для языкового стандарта C функция `iswxdigit` не поддерживает шестнадцатеричные символы Юникод полной ширины.  
  
 Версии этих функций с суффиксом `_l` используют переданный параметр языкового стандарта вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Поведение функций `isxdigit` и `_isxdigit_l` не определено, если `c` не является концом файла или не находится в диапазоне от 0 по 0xFF включительно. Если используется библиотека отладки CRT и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istxdigit`|`isxdigit`|`isxdigit`|`iswxdigit`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`isxdigit`|\<ctype.h>|  
|`iswxdigit`|\<ctype.h> или \<wchar.h>|  
|`_isxdigit_l`|\<ctype.h>|  
|`_iswxdigit_l`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)