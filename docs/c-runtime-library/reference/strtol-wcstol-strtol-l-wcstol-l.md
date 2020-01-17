---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 01/14/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: 83054e1b31b56fda96bdea198ab34d65d633f335
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123933"
---
# <a name="opno-locstrtol-opno-locwcstol-opno-loc_strtol_l-opno-loc_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Преобразует строки в **длинное** целое число.

## <a name="syntax"></a>Синтаксис

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*string*\
Строка, завершающаяся символом NULL, для преобразования.

*end_ptr*\
Выходной параметр, заданный для указания символа после последнего интерпретируемого символа. Игнорируется, если **значение равно NULL**.

*base*\
Используемое числовое основание.

\ *языкового стандарта*
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtol** , **wcstol** , **_strtol_l** и **_wcstol_l** возвращают значение, представленное в виде *строки*. Они возвращают 0, если преобразование невозможно. Когда представление вызовет переполнение, оно возвращает **LONG_MAX** или **LONG_MIN** .

**errno** имеет значение **ERANGE** , если происходит переполнение или потеря значимости. Он имеет значение **EINVAL** , если *строка* имеет **значение NULL**. Или, если значение *base* не равно нулю и меньше 2 или больше 36. Дополнительные сведения о **ERANGE** , **EINVAL** и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Заметки

Функции **strtol** , **wcstol** , **_strtol_l** и **_wcstol_l** преобразуют *строку* в **Long**. Они прекращают чтение *строки* с первого символа, который не распознается как часть числа. Это может быть завершающий символ null или первый буквенно-цифровой символ, который больше или равен *base*.

**wcstol** и **_wcstol_l** — это версии **strtol** и **_strtol_l** для расширенных символов. Их *строковый* аргумент является строкой расширенных символов. Эти функции ведут себя одинаково для **strtol** и **_strtol_l** иным образом. Параметр категории **LC_NUMERIC** языковой стандарт определяет распознавание символа системы счисления (маркер дробной части или десятичной запятой) в *строке*. Функции **strtol** и **wcstol** используют текущий языковой стандарт. **_strtol_l** и **_wcstol_l** использовать переданный языковой стандарт. Дополнительные сведения см. в разделе [setlocale] и [языковой стандарт](../../c-runtime-library/locale.md).

Если *end_ptr* имеет **значение NULL**, он игнорируется. В противном случае указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *end_ptr*. Преобразование невозможно, если не найдены допустимые цифры или указан недопустимый базовый. Затем значение *строки* сохраняется в расположении, на которое указывает *end_ptr*.

**strtol** *строка* должна указывать на строку следующего вида:

> [*пробел*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*буквенно-цифровые символы*]

В квадратных скобках (`[ ]`) необязательные элементы выделяются. Фигурные скобки и вертикальная черта (`{ | }`) заключаются в качестве альтернативы для одного элемента. *пробелы* могут состоять из пробелов и символов табуляции, которые игнорируются. *буквенно-цифровые* буквы являются десятичными цифрами или буквами от a до z (или от a до z). Первый символ, который не соответствует этой форме, останавливает проверку. Если значение *base* — от 2 до 36, то оно используется в качестве основания для числа. Если значение *base* равно 0, начальные символы строки, на которую указывает *строка* , используются для определения базового объекта. Если первый символ равен 0, а второй символ — не "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "a" до "z" (или от "A" до "Z") присваиваются значения от 10 до 35. Сканирование допускает только те буквы, значения которых меньше *базового*. Первый символ за пределами диапазона основания останавливает сканирование. Например, предположим, что *строка* начинается с «01». Если значение *base* равно 0, то средство проверки предполагает, что это восьмеричное целое число. Символ "8" или "9" останавливает сканирование.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> или \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> или \<wchar.h>|

Функции **_strtol_l** и **_wcstol_l** являются специфичными для Microsoft, а не частью стандартной библиотеки C. Дополнительные сведения о совместимости см. в разделе [Совместимость](../compatibility.md).

## <a name="example"></a>Пример

См. пример для [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>См. также:

\ [преобразования данных](../data-conversion.md)
[Языковой стандарт](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Функции типа "строка — числовое значение](../string-to-numeric-value-functions.md) "\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
