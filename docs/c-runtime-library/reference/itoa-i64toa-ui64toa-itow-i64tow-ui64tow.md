---
title: "_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_itow"
  - "_i64tow"
  - "_itoa"
  - "_i64toa"
  - "_ui64toa"
  - "_ui64tow"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_i64tow"
  - "ui64toa"
  - "ui64tow"
  - "itot"
  - "_itot"
  - "_i64toa"
  - "_itoa"
  - "_itow"
  - "_ui64tow"
  - "i64toa"
  - "i64tow"
  - "itow"
  - "_ui64toa"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_i64toa - функция"
  - "_i64tow - функция"
  - "_itoa - функция"
  - "_itot - функция"
  - "_itow - функция"
  - "_ui64toa - функция"
  - "_ui64tow - функция"
  - "преобразование целых чисел"
  - "преобразование чисел, к строкам"
  - "i64toa - функция"
  - "i64tow - функция"
  - "целые числа, преобразование"
  - "itoa - функция"
  - "itot - функция"
  - "itow - функция"
  - "ui64toa - функция"
  - "ui64tow - функция"
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует целое число в строку.  Существуют более безопасные версии этих функций; см. раздел [\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md).  
  
## Синтаксис  
  
```  
char *_itoa(  
   int value,  
   char *str,  
   int radix   
);  
char *_i64toa(  
   __int64 value,  
   char *str,  
   int radix   
);  
char * _ui64toa(  
   unsigned _int64 value,  
   char *str,  
   int radix   
);  
wchar_t * _itow(  
   int value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_itoa(  
   int value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char *_i64toa(  
   __int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char * _ui64toa(  
   unsigned _int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _itow(  
   int value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### Параметры  
 `value`  
 Число, которое нужно преобразовать.  
  
 `str`  
 Строковый результат.  
  
 `radix`  
 Основание системы счисления значения `value`; должно находиться в диапазоне от 2 до 36.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на `str`.  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 Функции `_itoa`, `_i64toa` и `_ui64toa` преобразуют цифры заданного аргумента `value` в символьную строку, завершающуюся символом null, и хранят результат \(до 33 символов для `_itoa` и 65 для `_i64toa` и `_ui64toa`\) в `str`.  Если `radix` равно 10 и `value` имеет отрицательное значение, то первым символом результирующей строки будет знак "минус" \( `–` \).  `_itow` `_i64tow` и `_ui64tow` \- версии функций `_itoa`, `_i64toa`, and `_ui64toa` для расширенных символов, соответственно.  
  
> [!IMPORTANT]
>  Чтобы предотвратить переполнение буфера, убедитесь, что буфер `str` достаточно велик для хранения преобразованных цифр, а также конечного символа null и символа знака.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_itot`|`_itoa`|`_itoa`|`_itow`|  
|`_i64tot`|`_i64toa`|`_i64toa`|`_i64tow`|  
|`_ui64tot`|`_ui64toa`|`_ui64toa`|`_ui64tow`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_itoa`|\<stdlib.h\>|  
|`_i64toa`|\<stdlib.h\>|  
|`_ui64toa`|\<stdlib.h\>|  
|`_itow`|\<stdlib.h\>|  
|`_i64tow`|\<stdlib.h\>|  
|`_ui64tow`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_itoa.c  
// compile with: /W3  
// This program makes use of the _itoa functions  
// in various examples.  
  
#include <string.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[65];  
   int r;  
   for( r=10; r>=2; --r )  
   {  
     _itoa( -1, buffer, r ); // C4996  
     // Note: _itoa is deprecated; consider using _itoa_s instead  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _i64toa( -1L, buffer, r ); // C4996  
     // Note: _i64toa is deprecated; consider using _i64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _ui64toa( 0xffffffffffffffffL, buffer, r ); // C4996  
     // Note: _ui64toa is deprecated; consider using _ui64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
}  
```  
  
  **base 10: \-1 \(2 chars\)**  
**base 9: 12068657453 \(11 chars\)**  
**base 8: 37777777777 \(11 chars\)**  
**base 7: 211301422353 \(12 chars\)**  
**base 6: 1550104015503 \(13 chars\)**  
**base 5: 32244002423140 \(14 chars\)**  
**base 4: 3333333333333333 \(16 chars\)**  
**base 3: 102002022201221111210 \(21 chars\)**  
**base 2: 11111111111111111111111111111111 \(32 chars\)**  
**base 10: \-1 \(2 chars\)**  
**base 9: 145808576354216723756 \(21 chars\)**  
**base 8: 1777777777777777777777 \(22 chars\)**  
**base 7: 45012021522523134134601 \(23 chars\)**  
**base 6: 3520522010102100444244423 \(25 chars\)**  
**base 5: 2214220303114400424121122430 \(28 chars\)**  
**base 4: 33333333333333333333333333333333 \(32 chars\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 chars\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 chars\)**  
**base 10: 18446744073709551615 \(20 chars\)**  
**base 9: 145808576354216723756 \(21 chars\)**  
**base 8: 1777777777777777777777 \(22 chars\)**  
**base 7: 45012021522523134134601 \(23 chars\)**  
**base 6: 3520522010102100444244423 \(25 chars\)**  
**base 5: 2214220303114400424121122430 \(28 chars\)**  
**base 4: 33333333333333333333333333333333 \(32 chars\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 chars\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 chars\)**   
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [\_ltoa, \_ltow](../Topic/_ltoa,%20_ltow.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s, \_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)