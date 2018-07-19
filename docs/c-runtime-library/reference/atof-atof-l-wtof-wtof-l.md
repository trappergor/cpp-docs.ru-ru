---
title: atof, _atof_l, _wtof, _wtof_l | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wtof_l
- atof
- _atof_l
- _wtof
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
- _tstof
- _ttof
- atof
- stdlib/atof
- math/atof
- _atof_l
- stdlib/_atof_l
- math/_atof_l
- _wtof
- corecrt_wstdlib/_wtof
- _wtof_l
- corecrt_wstdlib/_wtof_l
dev_langs:
- C++
helpviewer_keywords:
- tstof function
- atof_l function
- _atof_l function
- atof function
- _tstof function
- _ttof function
- wtof function
- _wtof_l function
- ttof function
- wtof_l function
- _wtof function
- string conversion, to floating point values
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78fe14783200e1e145c39b9b274d9e7e3ddb6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396814"
---
# <a name="atof-atofl-wtof-wtofl"></a>atof, _atof_l, _wtof, _wtof_l

Преобразуют строку в двойное значение.

## <a name="syntax"></a>Синтаксис

```C
double atof(
   const char *str
);
double _atof_l(
   const char *str,
   _locale_t locale
);
double _wtof(
   const wchar_t *str
);
double _wtof_l(
   const wchar_t *str,
   _locale_t locale
);
```

## <a name="parameters"></a>Параметры

*str*<br/>
Строка для преобразования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает **двойные** значение, порожденное методом интерпретации входных символов как числа. Возвращаемое значение равно 0,0, если аргумент невозможно преобразовать в значение этого типа.

Во всех случаях вне диапазона **errno** равно **ERANGE**. Если значение параметра, переданного в **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают значение 0.

## <a name="remarks"></a>Примечания

Эти функции преобразуют строку символов в значение двойной точности с плавающей запятой.

Входная строка представляет собой последовательность символов, которые могут обрабатываться как числовое значение указанного типа. Каждая функция прекращает чтение строки на первом знаке, который она не может распознать как часть числа. Этот символ может быть нуль-символом ("\0" или L"\0"), которым завершается строка.

*Str* аргумент **atof** и **_wtof** имеет следующий вид:

[*пробелов*] [*входа*] [*цифр*] [__.__ *цифр*] [{**e** &#124; **E** } [*входа*]*цифр*]

Объект *пробелов* состоит из пробелами или символами табуляции, которые игнорируются. *входа* либо плюс (+) или минус (-); и *цифр* — один или несколько десятичных цифр. Если перед десятичной запятой никаких цифр нет, после нее должен отображаться хотя бы один символ. Десятичные цифры может следовать показатель степени, которая состоит из вводной буквы (**e**, или **E**) и при необходимости десятичное целое число со знаком.

UCRT версии этих функций не поддерживается преобразование Fortran стиля (**d** или **D**) экспоненты буквы. Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют *языкового стандарта* параметры, переданные в вместо текущего языкового стандарта.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstof**|**atof**|**atof**|**_wtof**|
|**_ttof**|**atof**|**atof**|**_wtof**|

## <a name="requirements"></a>Требования

|Routine(s)|Обязательный заголовок|
|------------------|---------------------|
|**atof**, **_atof_l**|C: \<math.h> или \<stdlib.h> C++: \<cstdlib>, \<stdlib.h>, \<cmath> или \<math.h>|
|**_wtof**, **_wtof_l**|C: \<stdlib.h> или \<wchar.h> C++: \<cstdlib>, \<stdlib.h> или \<wchar.h>|

## <a name="example"></a>Пример

Эта программа показывает, как числа, сохраненные в виде строк можно преобразовать в числовые значения с помощью **atof** и **_atof_l** функции.

```C
// crt_atof.c
//
// This program shows how numbers stored as
// strings can be converted to numeric
// values using the atof and _atof_l functions.

#include <stdlib.h>
#include <stdio.h>
#include <locale.h>

int main(void)
{
    char    *str = NULL;
    double value = 0;
    _locale_t fr = _create_locale(LC_NUMERIC, "fr-FR");

    // An example of the atof function
    // using leading and training spaces.
    str = "  3336402735171707160320 ";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // Another example of the atof function
    // using the 'E' exponential formatting keyword.
    str = "3.1412764583E210";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // An example of the atof and _atof_l functions
    // using the 'e' exponential formatting keyword
    // and showing different decimal point interpretations.
    str = "  -2,309e-25";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);
    value = _atof_l(str, fr);
    printf("Function: _atof_l(\"%s\", fr)) = %e\n", str, value);
}
```

```Output
Function: atof("  3336402735171707160320 ") = 3.336403e+21
Function: atof("3.1412764583E210") = 3.141276e+210
Function: atof("  -2,309e-25") = -2.000000e+00
Function: _atof_l("  -2,309e-25", fr)) = -2.309000e-25
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
