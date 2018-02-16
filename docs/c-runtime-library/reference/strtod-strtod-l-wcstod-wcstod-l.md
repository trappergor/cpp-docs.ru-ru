---
title: "strtod, _strtod_l, wcstod, _wcstod_l | Документы Майкрософт"
ms.custom: 
ms.date: 10/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
dev_langs:
- C++
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe18737b52ba2b04e3ee09813c6b48b6ebdf0363
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

Преобразование строки в значение двойной точности.

## <a name="syntax"></a>Синтаксис

```C
double strtod(
   const char *nptr,
   char **endptr
);
double _strtod_l(
   const char *nptr,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *nptr,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *nptr,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*nptr*  
Строка, завершающаяся символом NULL, для преобразования.

*endptr*  
Указатель на символ, который останавливает сканирование.

*locale*  
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

`strtod` Возвращает значение числа с плавающей запятой, за исключением случаев, когда представление вызвало бы переполнение, в котором случае функция возвращает +/-`HUGE_VAL`. Знак `HUGE_VAL` соответствует знаку значения, которое не может быть представлено. `strtod` возвращает 0, если преобразование не может быть выполнено или происходит потеря значимости.

Функция `wcstod` возвращает значения аналогично функции `strtod`. Для обеих функций `errno` получает значение `ERANGE` при возникновении переполнения или потери значимости, и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Примечания

Каждая функция преобразует входную строку *nptr* для `double`. `strtod` Функция преобразует *nptr* значение двойной точности. `strtod` прекращает чтение строки *nptr* с первого символа, не удается распознать как часть числа. Это может быть завершающий нуль-символ. `wcstod` — это двухбайтовая версия `strtod`; его *nptr* аргумент представляет собой строку расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcstod`|`strtod`|`strtod`|`wcstod`|
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|

`LC_NUMERIC` Текущего языкового стандарта категория определяет распознавание символа системы счисления точки в *nptr*. Дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции без `_l` суффикс используют текущий языковой стандарт; `_strtod_l` идентична `_strtod_l` за исключением того, что они используют *языкового стандарта* переданный. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не `NULL`, указатель на символ, который остановлена сканирования хранится в расположении, указанном *endptr*. Если преобразование не может быть выполнена (не найдены допустимые цифры или указано недопустимое основание), значение *nptr* хранится в расположении, указанном *endptr*.

`strtod` ожидает *nptr* для указания строка одного из следующих форм:

[*пробелов*] [*входа*] {*цифр* [*основание системы счисления* *цифр*] &#124; *основание системы счисления* *цифр*} [{**e** &#124; **E**} [*входа*] *цифр*]  
[*пробелов*] [*входа*] {**0 x** &#124; **0 X**} {*hexdigits* [*основание системы счисления* *hexdigits*] &#124; *основание системы счисления* *hexdigits*} [{**p** &#124; **P**} [*входа*] *hexdigits*]  
[*пробелов*] [*входа*] {**INF** &#124; **Бесконечность**}  
[*whitespace*] [*sign*] **NAN** [*sequence*]

Необязательные открывающие *пробелов* может состоять из пробелов и символов табуляции, которые игнорируются. *входа* либо плюс (+) или минус (-); *цифр* — один или несколько десятичных цифр; *hexdigits* — один или несколько шестнадцатеричных цифр; *основание системы счисления* является символ точки основание системы счисления, либо точка (.) в языковом стандарте «C» по умолчанию, или значение языковому стандарту текущего языкового стандарта, отличается ли при *языкового стандарта* задан; *последовательности* — это последовательность алфавитно-цифровых символов или символы подчеркивания. В формах десятичным и шестнадцатеричным номеров Если отображается без знаков перед символом точки основание системы счисления, по крайней мере один должен находиться после символа точки основание системы счисления. В десятичном формате десятичных разрядов может следовать показатель степени, которая состоит из вводной буквы (**e** или **E**) и при необходимости знаковое целое число. В шестнадцатеричной форме шестнадцатеричными цифрами может следовать показатель степени, которая состоит из вводной буквы (**p** или **P**) и при необходимости шестнадцатеричное целое число со знаком, представляющее показатель степени как степенью числа 2. В любой форме, если появится символ точки основание системы счисления ни одним из аспектов показатель степени, символ точки основание системы счисления предполагается выполните последний знак в строке. Регистр учитывается в обоих **INF** и **NAN** форм. Первый символ, который не соответствует ни одной из этих форм останавливает проверку.

UCRT версии этих функций не поддерживается преобразование Fortran стиля (**d** или **D**) экспоненты буквы. Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода. Версии UCRT поддерживают шестнадцатеричных строк и кругового пути значения INF и NAN, которые не поддерживались в более ранних версиях. Это также может вызвать критические изменения в коде. Например, строка «0x1a» будет интерпретироваться по `strtod` 0,0 в предыдущих версиях, а 26.0 в версии UCRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`strtod`, `_strtod_l`|C: &lt;stdlib.h> C++: &lt;cstdlib> или &lt;stdlib.h> |
|`wcstod`, `_wcstod_l`|C: &lt;stdlib.h> или &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> или &lt;wchar.h> |

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)   
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
[Языковой стандарт](../../c-runtime-library/locale.md)   
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
[strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
[atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
[localeconv](../../c-runtime-library/reference/localeconv.md)   
[_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
[_free_locale](../../c-runtime-library/reference/free-locale.md)