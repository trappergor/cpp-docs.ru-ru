---
title: "isdigit, iswdigit, _isdigit_l, _iswdigit_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isdigit_l"
  - "iswdigit"
  - "_iswdigit_l"
  - "isdigit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_iswdigit_l"
  - "_isdigit_l"
  - "iswdigit"
  - "isdigit"
  - "_istdigit"
  - "_istdigit_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iswdigit - функция"
  - "iswdigit_l - функция"
  - "_iswdigit_l - функция"
  - "_istdigit_l - функция"
  - "_istdigit - функция"
  - "istdigit - функция"
  - "isdigit - функция"
  - "isdigit_l - функция"
  - "_ismbcdigit_l - функция"
  - "_isdigit_l - функция"
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isdigit, iswdigit, _isdigit_l, _iswdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, представляет ли целое число символ десятичной цифры.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает отличное от нуля значение, если `c` — конкретное представление символа десятичной цифры.  `isdigit` возвращает ненулевое значение, если `c` десятичный цифра \(от 0 до 9\).  `iswdigit` возвращает ненулевое значение, если `c` расширенный символ, который соответствует символу десятичного разряда.  Каждая из этих процедур возвращает 0, если `c` не удовлетворяет условию теста.  
  
 Версии этих функций, которые содержат суффикс `_l` для поведения, зависящего от языкового стандарта, используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Поведение `isdigit` и `_isdigit_l` является неопределенным, если `c` не является концом файла или не находится в диапазоне от 0 до 0xFF включительно.  При использовании библиотеки CRT отладки и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istdigit`|`isdigit`|[\_ismbcdigit](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|`iswdigit`|  
|`_istdigit_l`|`_isdigit_l`|[\_ismbcdigit\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|`_iswdigit_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`isdigit`|\<ctype.h\>|  
|`iswdigit`|\<ctype.h\> или \<wchar.h\>|  
|`_isdigit_l`|\<ctype.h\>|  
|`_iswdigit_l`|\<ctype.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)