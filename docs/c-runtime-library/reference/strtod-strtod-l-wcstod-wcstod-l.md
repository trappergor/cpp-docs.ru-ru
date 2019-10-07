---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 10/20/2017
api_name:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 5372525eb99dc9d39e31b10def0377c9aad5296c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946492"
---
# <a name="strtod-_strtod_l-wcstod-_wcstod_l"></a>strtod, _strtod_l, wcstod, _wcstod_l

Преобразование строки в значение двойной точности.

## <a name="syntax"></a>Синтаксис

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*стрсаурце*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*ендптр*<br/>
Указатель на символ, который останавливает сканирование.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtod** возвращает значение числа с плавающей запятой, за исключением случаев, когда представление вызовет переполнение, в этом случае функция возвращает +/-**HUGE_VAL**. Знак **HUGE_VAL** соответствует знаку значения, которое не может быть представлено. **strtod** возвращает 0, если не удается выполнить преобразование или происходит потеря значимости.

**wcstod** возвращает значения по аналогии с **strtod**. Для обеих функций параметру **ERANGE** присваивается **значение, если** происходит переполнение или потеря значимости, и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая функция преобразует входную строку *стрсаурце* в значение **типа Double**. Функция **strtod** преобразует *стрсаурце* в значение двойной точности. **strtod** прекращает чтение строки *стрсаурце* на первом символе, который он не может распознать как часть числа. Это может быть завершающий нуль-символ. **wcstod** — это версия **strtod**для расширенных символов; его аргумент *стрсаурце* является строкой расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Параметр категории **LC_NUMERIC** текущего языкового стандарта определяет распознавание символа точки основания в *стрсаурце*. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции без суффикса **_l** используют текущий языковой стандарт. **_strtod_l** идентичен **_strtod_l** , за исключением того, что они используют переданный *языковой стандарт* . Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *ендптр* не равно **null**, то указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *ендптр*. Если не удается выполнить преобразование (не найдены допустимые цифры или указана недопустимая база), значение *стрсаурце* хранится в расположении, на которое указывает *ендптр*.

**strtod** ждет, что *стрсаурце* указывает на строку одной из следующих форм:

[*пробел*] [*Sign*] {*цифры* [ *цифры*системы счисления &#124; ] *цифры*системы *счисления* } [{**e** &#124; **e**} [*знак*] *цифры*] [*пробел*] [*знак*] {**0x** &#124; **0x**} {*хексдигитс* [*основание системы счисления* *хексдигитс*] &#124;  *основание системы счисления* *хексдигитс*} [{**p** &#124; **p**} [*Sign*] *хексдигитс*] [*пробел*] [*Sign*] {**INF** &#124; **Infinity**} [*пробел*] *[ Sign*] **NaN** [*последовательность*]

Необязательный начальный *пробел* может состоять из пробелов и символов табуляции, которые игнорируются; *знак* «плюс» (+) или «минус» (-); *цифры* — это одна или несколько десятичных цифр; *хексдигитс* — одна или несколько шестнадцатеричных цифр; *основание* системы счисления — это символ точки основания, точка (.) в языковом стандарте "C" по умолчанию или значение, зависящее от языкового стандарта, если текущий языковой стандарт отличается от языка или если указан *языковой* стандарт. *последовательность* — это последовательность буквенно-цифровых символов или знаков подчеркивания. В формах десятичных и шестнадцатеричных чисел, если перед символом точки основания не отображаются цифры, по крайней мере один из них должен располагаться после символа точки основания. В десятичной форме за десятичными цифрами может следовать показатель степени, состоящий из вводной буквы (**e** или **e**) и необязательного целого числа со знаком. В шестнадцатеричной форме за шестнадцатеричными цифрами может следовать экспонента, которая состоит из вводной буквы (**p** или **p**) и необязательного шестнадцатеричного целого числа со знаком, представляющего экспоненту как степень числа 2. В любой форме, если не отображается ни часть экспоненты, ни символ точки основания, предполагается, что символ точки основания соответствует последней цифре в строке. Регистр игнорируется в формах **INF** и **NaN** . Первый символ, который не соответствует ни одной из этих форм, останавливает проверку.

UCRT версии этих функций не поддерживают преобразование букв экспоненты в стиле Fortran (**d** или **d**). Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода. Версии UCRT поддерживают шестнадцатеричные строки и циклический обмен значениями INF и NAN, которые не поддерживались в более ранних версиях. Это также может привести к критическим изменениям в коде. Например, строка "0x1a" будет интерпретирована **strtod** как 0,0 в предыдущих версиях, но как 26,0 в версии UCRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> или &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> или &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> или &lt;wchar.h> |

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

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
