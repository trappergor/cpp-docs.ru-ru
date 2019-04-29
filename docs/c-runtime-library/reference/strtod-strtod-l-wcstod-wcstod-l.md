---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 10/20/2017
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
ms.openlocfilehash: c8c2b3b491e2e7265829fa88580529dc757ace8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376475"
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

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

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtod** возвращает значение числа с плавающей запятой, за исключением случаев, когда представление вызвало бы переполнение, в котором случае функция возвращает +/-**HUGE_VAL**. Знак **HUGE_VAL** соответствует знаку значения, которое не может быть представлено. **strtod** возвращает 0, если преобразование не может быть выполнено или происходит потеря значимости.

**wcstod** возвращает значения аналогично функции **strtod**. Для обеих функций **errno** присваивается **ERANGE** при возникновении переполнения или потери значимости, и вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая функция преобразует входную строку *strSource* для **двойные**. **Strtod** функция преобразует *strSource* в значение двойной точности. **strtod** прекращает чтение строки *strSource* на первом знаке, она не может распознать как часть числа. Это может быть завершающий нуль-символ. **wcstod** — это двухбайтовая версия **strtod**; его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

**LC_NUMERIC** параметр категории текущего языкового стандарта определяет распознавание символа системы счисления точки в *strSource*. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции, не имеющие **_l** суффикс используют текущий языковой стандарт; **_strtod_l** идентична **_strtod_l** за исключением того, что они используют *языкового стандарта* переданный в качестве. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который останавливает сканирование, хранится в расположении, указанном *endptr*. Если преобразование не может быть выполнено (найдены нет допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, указанном *endptr*.

**strtod** ожидает *strSource* указывает строку одного из следующих форм:

[*пробелы*] [*входа*] {*цифр* [*основание системы счисления* *цифр*] &#124;  *Основание системы счисления* *цифр*} [{**e** &#124; **E**} [*входа*] *цифр*] [*пробелы*] [*входа*] {**0 x** &#124; **0 X**} {*hexdigits* [ *основание системы счисления* *hexdigits*] &#124; *основание системы счисления* *hexdigits*} [{**p** &#124; **P**} [*входа*] *hexdigits*] [*пробелы*] [*входа*] {} **INF** &#124; **бесконечность**} [*пробелы*] [*входа*]  **NAN** [*последовательности*]

Необязательный начальный символ *пробелы* может состоять из пробелов и символов табуляции, которые игнорируются; *входа* либо плюс (+) или минус (–); *цифр* — один или несколько десятичных цифр; *hexdigits* — один или несколько шестнадцатеричных цифр; *основание системы счисления* находится точка символа системы счисления, либо точка (.) в языковом стандарте «C» по умолчанию, или значение зависящих от языкового стандарта, если текущий языковой стандарт отличается или при *языкового стандарта* задан; *последовательности* представляет собой последовательность из букв, цифр и символов подчеркивания. В различных формах десятичные и шестнадцатеричные Если отображается без знаков перед символом основания системы счисления точки, по крайней мере должны располагаться после точки символа системы счисления. В десятичной форме, за десятичными цифрами может следовать показатель степени, который состоит из вводной буквы (**e** или **E**) и при необходимости целым. В шестнадцатеричной форме, шестнадцатеричных цифр может следовать показатель степени, который состоит из вводной буквы (**p** или **P**) и при необходимости шестнадцатеричное целое число со знаком, представляющее показатель степени как степень числа 2. В любой форме ни экспоненциальная часть, ни символ основания системы счисления точки в открывшемся символ основания системы счисления точка считается за последней цифрой в строке. Регистр учитывается в обоих **INF** и **NAN** форм. Первый символ, который не соответствует ни одному из этих форм останавливает сканирование.

UCRT-версии этих функций не поддерживают преобразование стиле Fortran (**d** или **D**) экспонент. Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода. UCRT-версии поддерживает шестнадцатеричные строки и совместимость значения INF и NAN, которые не поддерживались в более ранних версиях. Это также может вызвать критические изменения в коде. Например, строка «0x1a» будет интерпретироваться в соответствии с путем **strtod** 0,0 в предыдущих версиях, а также как 26.0 в версии UCRT.

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
