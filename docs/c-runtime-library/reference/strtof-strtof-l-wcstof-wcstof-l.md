---
title: strtof, _strtof_l, wcstof, _wcstof_l
ms.date: 04/05/2018
api_name:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
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
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
ms.openlocfilehash: b2b2e7d230074b5a464260d36b41c28b9951d65b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957748"
---
# <a name="strtof-_strtof_l-wcstof-_wcstof_l"></a>strtof, _strtof_l, wcstof, _wcstof_l

Преобразует строки в значение одиночной точности с плавающей точкой.

## <a name="syntax"></a>Синтаксис

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>Параметры

*стрсаурце*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*ендптр*<br/>
Указатель на символ, который останавливает сканирование.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtof** возвращает значение числа с плавающей запятой, за исключением случаев, когда представление вызовет переполнение, в этом случае функция возвращает +/-**HUGE_VALF**. Знак **HUGE_VALF** соответствует знаку значения, которое не может быть представлено. **strtof** возвращает 0, если не удается выполнить преобразование или происходит потеря значимости.

**wcstof** возвращает значения по аналогии с **strtof**. Для обеих функций параметру **ERANGE** присваивается **значение, если** происходит переполнение или потеря значимости, и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая функция преобразует входную строку *стрсаурце* в тип **float**. Функция **strtof** преобразует *стрсаурце* в значение с одной точностью. **strtof** прекращает чтение строки *стрсаурце* на первом символе, который он не может распознать как часть числа. Это может быть завершающий нуль-символ. **wcstof** — это версия **strtof**для расширенных символов; его аргумент *стрсаурце* является строкой расширенных символов. В остальном эти функции работают одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

Параметр категории **LC_NUMERIC** текущего языкового стандарта определяет распознавание символа системы счисления в *стрсаурце*; Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, у которых нет суффикса **_l** , используют текущий языковой стандарт. имена, имеющие суффикс, идентичны, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *ендптр* не равно **null**, то указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *ендптр*. Если не удается выполнить преобразование (не найдены допустимые цифры или указана недопустимая база), значение *стрсаурце* хранится в расположении, на которое указывает *ендптр*.

**strtof** ждет, что *стрсаурце* указывает на строку следующего вида:

[*пробел*] [*Sign*] [*цифры*] [ __.__ *цифры*] [{**e** &#124; **e**} [*знак*] *цифры*]

*Пробелы* могут состоять из пробелов и символов табуляции, которые игнорируются; *знак* «плюс» ( **+** ) или «минус **-** » (); *цифры* — одна или несколько десятичных цифр. Если перед символом основания системы счисления нет никаких цифр, то после него должна отображаться хотя бы одна цифра. За десятичными цифрами может следовать показатель степени, состоящий из вводной буквы (**e** или **e**) и необязательного целого числа со знаком. Если не отображается ни экспоненциальная часть, ни символ основания системы счисления, то предполагается, что символ основания системы счисления следует за последней цифрой в строке. Первый символ, который не соответствует этой форме, останавливает сканирование.

UCRT версии этих функций не поддерживают преобразование букв экспоненты в стиле Fortran (**d** или **d**). Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<stdlib.h> C++: &lt;cstdlib> или \<stdlib.h>|
|**wcstof**, **_wcstof_l**|C: \<stdlib.h> или \<wchar.h> C++: &lt;cstdlib>, \<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
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
