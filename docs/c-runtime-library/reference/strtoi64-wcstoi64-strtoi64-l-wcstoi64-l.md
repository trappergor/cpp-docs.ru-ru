---
title: _strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l
ms.date: 11/04/2016
apiname:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
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
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
ms.openlocfilehash: a8097a31ebbc56281008f14da58671d5b2e4e8b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490783"
---
# <a name="strtoi64-wcstoi64-strtoi64l-wcstoi64l"></a>_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l

Преобразуют строку в **__int64** значение.

## <a name="syntax"></a>Синтаксис

```C
__int64 _strtoi64(
   const char *strSource,
   char **endptr,
   int base
);
__int64 _wcstoi64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
__int64 _strtoi64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
__int64 _wcstoi64_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*base*<br/>
Используемое числовое основание.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_strtoi64** возвращает значение, представленное в строке *strSource*, кроме случаев, когда представление вызвало бы переполнение, в этом случае он возвращает **_I64_MAX** или **_I64 _MIN**. Функция возвращает 0, если преобразование не может быть выполнено. **_wcstoi64** возвращает значения аналогично функции **strtoi64**.

**_I64_MAX** и **_I64_MIN** определенные ограничения. З.

Если *strSource* — **NULL** или *базового* имеет ненулевое значение и либо меньше 2 или больше 36, **errno** присваивается **EINVAL** .

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Strtoi64** функция преобразует *strSource* для **__int64**. Обе функции прекращают чтение строки *strSource* на первом знаке, они не может распознать как часть числа. Это может быть завершающий нуль-символ, или он может быть первый числовой символ больше или равно *базового*. **_wcstoi64** — это двухбайтовая версия **_strtoi64**; его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoi64**|**_strtoi64**|**_strtoi64**|**_wcstoi64**|
|**_tcstoi64_l**|**_strtoi64_l**|**_strtoi64_l**|**_wcstoi64_l**|

Языкового стандарта **LC_NUMERIC** параметр category определяет распознавание символа основания системы счисления в *strSource **;* Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции, не имеющие суффикса _l используют текущий языковой стандарт; **_strtoi64_l** и **_wcstoi64_l** идентичны соответствующей функции без **_l** суффикса, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который останавливает сканирование, хранится в расположении, указанном *endptr*. Если преобразование не может быть выполнено (найдены нет допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, указанном *endptr*.

**_strtoi64** ожидает *strSource* указывает строку следующего вида:

> [*пробелы*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*цифр* &#124; *буквы*]  

Объект *пробелы* может состоять из пробелов и символов табуляции, которые игнорируются; *цифр* — один или несколько десятичных цифр; *буквы* имеют один или несколько букв «» до «z» (или «A» до «Z»).  Первый символ, который не соответствует этой форме, останавливает сканирование. Если *базового* — от 2 до 36, то он используется как основание системы счисления. Если *базового* равно 0, то начальные символы строки, на которые указывают *strSource* используются для определения основания. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например если *базового* 0 и первый считанный символ — "0", предполагается восьмеричное целое число и символ "8" или "9" остановит сканирование.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strtoi64**, **_strtoi64_l**|\<stdlib.h>|
|**_wcstoi64**, **_wcstoi64_l**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
