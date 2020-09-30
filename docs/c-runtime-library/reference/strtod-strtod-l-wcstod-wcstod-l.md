---
title: strtod, _strtod_l, wcstod, _wcstod_l
description: Справочник по API для strtod, _strtod_l, wcstod и _wcstod_l; , который преобразует строки в значение двойной точности.
ms.date: 08/27/2020
api_name:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
- _o__strtod_l
- _o__wcstod_l
- _o_strtod
- _o_wcstod
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 5a791b5d0be218a49be28930c191de3eb4acf4be
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505547"
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

**strtod** возвращает значение числа с плавающей запятой, за исключением случаев, когда представление приведет к переполнению, в этом случае функция возвращает +/-**HUGE_VAL**. Знак **HUGE_VAL** соответствует знаку значения, которое не может быть представлено. **strtod** возвращает, `0` если не удается выполнить преобразование или происходит потеря значимости.

**wcstod** возвращает значения по аналогии с **strtod**:

- Для обеих **функций в случае** переполнения или потери значимости устанавливается значение **ERANGE** .
- Если присутствуют недопустимые **Параметры, для** параметра « **еинвал** » задается значение «равно» и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, Code/Code, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая функция преобразует входную строку *стрсаурце* в **`double`** . Функция **strtod** преобразует *стрсаурце* в значение двойной точности. **strtod** прекращает чтение строки *стрсаурце* на первом символе, который он не может распознать как часть числа. Этот символ может быть завершающим нулевым символом. **wcstod** — это версия **strtod**для расширенных символов; его аргумент *стрсаурце* является строкой расширенных символов. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Параметр категории **LC_NUMERIC** текущего языкового стандарта определяет распознавание символа точки основания в *стрсаурце*. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции без суффикса **_l** используют текущий языковой стандарт; **_strtod_l** идентична **_strtod** за исключением того, что в прежнем случае используется переданный *языковой стандарт* . Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *ендптр* не **равно NULL**, то указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *ендптр*. Если не удается выполнить преобразование (не найдены допустимые цифры или указана недопустимая база), значение *стрсаурце* хранится в расположении, на которое указывает *ендптр*.

**strtod** ждет, что *стрсаурце* указывает на строку одной из следующих форм:

[*пробел*] [*Sign*] {*цифры* [*radix* *цифры*системы счисления] &#124; *цифры*системы *счисления* } [{**e** &#124; **e**} [*знак*] *цифры*] [*пробел*] [*знак*] {**0x** &#124; **0x**} {*хексдигитс* [*основание* *хексдигитс*] &#124; *основание системы счисления* *hexdigits*] [{**p** &#124; **p**} [*знак*] *цифры*] [*пробел*] [*знак*] {**INF** &#124; **бесконечность**} [*пробел*] [*знак*] **NaN** [*последовательность*]

Необязательный начальный *пробел* может состоять из пробелов и символов табуляции, которые игнорируются.
*знак* «плюс» (+) или «минус» (-). \
*цифры* — одна или несколько десятичных цифр. \
*хексдигитс* — одна или несколько шестнадцатеричных цифр. \
*основание* системы счисления — это символ точки основания или точка (.) в языковом стандарте "C" по умолчанию, или значение, зависящее от языкового стандарта, если текущий языковой стандарт отличается от *заданного языкового* стандарта. \
 *Последовательность* — это последовательность буквенно-цифровых символов или знаков подчеркивания.

В формах десятичных и шестнадцатеричных чисел, если перед символом точки основания не отображаются цифры, по крайней мере один из них должен располагаться после символа точки основания.

В десятичной форме за десятичными цифрами может следовать показатель степени, состоящий из вводной буквы (**e** или **e**) и необязательного целого числа со знаком.

В шестнадцатеричной форме за шестнадцатеричными цифрами может следовать экспонента, которая состоит из вводной буквы (**p** или **p**) и необязательного десятичного целого числа со знаком, представляющего экспоненту как степень числа 2.

В любой форме, если отсутствует часть экспоненты или символ точки основания, предполагается, что символ точки основания соответствует последней цифре в строке.

Регистр игнорируется в формах **INF** и **NaN** . Первый символ, который не соответствует ни одной из этих форм, останавливает проверку.

UCRT версии этих функций не поддерживают преобразование букв экспоненты в стиле Fortran (**d** или **d**). Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода. Версии UCRT поддерживают шестнадцатеричные строки и циклический обмен значениями INF и NAN, которые не поддерживались в более ранних версиях. Это также может привести к критическим изменениям в коде. Например, строка "0x1a" будет интерпретирована **strtod** как 0,0 в предыдущих версиях, но как 26,0 в версии UCRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> или &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> или &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> или &lt;wchar.h> |

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Функции типа "строка — числовое значение"](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
