---
title: strtold, _strtold_l, wcstold, _wcstold_l
ms.date: 04/05/2018
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
ms.openlocfilehash: fce60775ee1ef6def214e559779004d4de95453c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484582"
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l

Преобразует строки в значение long двойной точности с плавающей точкой.

## <a name="syntax"></a>Синтаксис

```C
long double strtold(
   const char *strSource,
   char **endptr
);
long double _strtold_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
long double wcstold(
   const wchar_t *strSource,
   wchar_t **endptr
);
long double wcstold_l(
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

**strtold** возвращает значение числа с плавающей запятой как **long** **двойные**, за исключением случаев, когда представление вызвало бы переполнение — в этом случае функция возвращает +/-**HUGE_VALL**. Знак **HUGE_VALL** соответствует знаку значения, которое не может быть представлено. **strtold** возвращает 0, если преобразование не может быть выполнено или происходит потеря значимости.

**wcstold** возвращает значения аналогично функции **strtold**. Для обеих функций **errno** присваивается **ERANGE** при возникновении переполнения или потери значимости, и вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая функция преобразует входную строку *strSource* для **long** **двойные**. **Strtold** каждая функция прекращает чтение строки *strSource* на первом знаке, она не может распознать как часть числа. Это может быть завершающий нуль-символ. Двухбайтовая версия **strtold** — **wcstold**; его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции работают одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

**LC_NUMERIC** параметр категории текущего языкового стандарта определяет распознавание символа основания системы счисления в *strSource*. Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, не имеющие **_l** суффикс используют текущий языковой стандарт; **_strtold_l** и **_wcstold_l** идентичны **_strtold** и **_wcstold** за исключением того, что они используют языковой стандарт на Переданный. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который останавливает сканирование, хранится в расположении, указанном *endptr*. Если преобразование не может быть выполнено (найдены нет допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, указанном *endptr*.

**strtold** ожидает *strSource* указывает строку следующего вида:

[*пробелы*] [*входа*] [*цифр*] [. *цифры*] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*входа* ]*цифр*]

Объект *пробелы* может состоять из пробелов и символов табуляции, которые игнорируются; *входа* либо плюс (**+**) или "минус" (**-**); и *цифр* — один или несколько десятичных цифр. Если перед символом основания системы счисления нет никаких цифр, то после него должна отображаться хотя бы одна цифра. За десятичными цифрами может следовать показатель степени, который состоит из вводной буквы (**d**, **D**, **e**или **E**) и, при необходимости, целого числа со знаком. Если не отображается ни экспоненциальная часть, ни символ основания системы счисления, то предполагается, что символ основания системы счисления следует за последней цифрой в строке. Первый символ, который не соответствует этой форме, останавливает сканирование.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtold**, **_strtold_l**|\<stdlib.h>|
|**wcstold**, **_wcstold_l**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtold.c
// Build with: cl /W4 /Tc crt_strtold.c
// This program uses strtold to convert a
// string to a long double-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   long double x;

   string = "3.1415926535898This stopped it";
   x = strtold(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtold = %.13Lf\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.1415926535898This stopped it
   strtold = 3.1415926535898
   Stopped scan at: This stopped it

```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
