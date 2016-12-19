---
title: "_itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s | Microsoft Docs"
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
  - "_ui64tow_s"
  - "_itoa_s"
  - "_itow_s"
  - "_ui64toa_s"
  - "_i64tow_s"
  - "_i64toa_s"
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
  - "i64tot_s"
  - "itow_s"
  - "_ui64tow_s"
  - "_itow_s"
  - "ui64tot_s"
  - "_ui64toa_s"
  - "itoa_s"
  - "_i64tow_s"
  - "_i64tot_s"
  - "_itot_s"
  - "_i64toa_s"
  - "_itoa_s"
  - "ui64toa_s"
  - "i64toa_s"
  - "_ui64tot_s"
  - "i64tow_s"
  - "itot_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_i64toa_s - функция"
  - "_i64tot_s - функция"
  - "_i64tow_s - функция"
  - "_itoa_s - функция"
  - "_itot_s - функция"
  - "_itow_s - функция"
  - "_ui64toa_s - функция"
  - "_ui64tot_s - функция"
  - "_ui64tow_s - функция"
  - "преобразование целых чисел"
  - "преобразование чисел, к строкам"
  - "i64toa_s - функция"
  - "i64tow_s - функция"
  - "целые числа, преобразование"
  - "itoa_s - функция"
  - "itow_s - функция"
  - "ui64toa_s - функция"
ms.assetid: eb746581-bff3-48b5-a973-bfc0a4478ecf
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует целое число в строку.  Здесь представлены версии [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _itoa_s(  
   int value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64toa_s(  
   __int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64toa_s(  
   unsigned _int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _itow_s(  
   int value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64tow_s(  
   __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64tow_s(  
   unsigned __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
template <size_t size>  
errno_t _itoa_s(  
   int value,  
   char (&buffer)[size],  
   int radix   
); // C++ only  
template <size_t size>  
errno_t _itow_s(  
   int value,  
   wchar_t (&buffer)[size],  
   int radix   
); // C++ only  
```  
  
#### Параметры  
 \[входящий\] `value`  
 Число, которое нужно преобразовать.  
  
 \[исходящий\] `buffer`  
 Заполняется результатом преобразования.  
  
 \[входящий\] `sizeInCharacters`  
 Размер буфера в однобайтовых или расширенных символах.  
  
 \[входящий\] `radix`  
 Основание системы счисления значения `value`; должно находиться в диапазоне от 2 до 36.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  Если применяются любые из следующих условий, функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
### Условия возникновения ошибки  
  
|value|buffer|sizeInCharacters|radix|Return|  
|-----------|------------|----------------------|-----------|------------|  
|any|`NULL`|any|any|`EINVAL`|  
|any|any|\<\=0|any|`EINVAL`|  
|any|any|\<\= длина требуемой результирующей строки|any|`EINVAL`|  
|any|any|any|`radix` \< 2 или `radix` \> 36|`EINVAL`|  
  
 **Проблемы безопасности**  
  
 Эти функции могут создавать нарушение прав доступа, если `buffer` не указывает на допустимую память и не равен `NULL`, или если длина буфера недостаточна для хранения результирующей строки.  
  
## Заметки  
 За исключением параметров и возвращаемого значения, функции `_itoa_s` имеют одинаковое поведение с соответствующими менее безопасными версиями.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_itot_s`|`_itoa_s`|`_itoa_s`|`_itow_s`|  
|`_i64tot_s`|`_i64toa_s`|`_i64toa_s`|`_i64tow_s`|  
|`_ui64tot_s`|`_ui64toa_s`|`_ui64toa_s`|`_ui64tow_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_itoa_s`|\<stdlib.h\>|  
|`_i64toa_s`|\<stdlib.h\>|  
|`_ui64toa_s`|\<stdlib.h\>|  
|`_itow_s`|\<stdlib.h\> или \<wchar.h\>|  
|`_i64tow_s`|\<stdlib.h\> или \<wchar.h\>|  
|`_ui64tow_s`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_itoa_s.c  
#include <stdlib.h>  
#include <string.h>  
  
int main( void )  
{  
    char buffer[65];  
    int r;  
    for( r=10; r>=2; --r )  
    {  
       _itoa_s( -1, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _i64toa_s( -1L, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _ui64toa_s( 0xffffffffffffffffL, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
}  
```  
  
## Output  
  
```  
base 10: -1 (2 chars)  
base 9: 12068657453 (11 chars)  
base 8: 37777777777 (11 chars)  
base 7: 211301422353 (12 chars)  
base 6: 1550104015503 (13 chars)  
base 5: 32244002423140 (14 chars)  
base 4: 3333333333333333 (16 chars)  
base 3: 102002022201221111210 (21 chars)  
base 2: 11111111111111111111111111111111 (32 chars)  
  
base 10: -1 (2 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
  
base 10: 18446744073709551615 (20 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
```  
  
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [\_ltoa, \_ltow](../Topic/_ltoa,%20_ltow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)