---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 11/04/2016
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
ms.openlocfilehash: b40362e93a41730e46ad0911b5a633118d024e9c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957634"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Преобразует строки в целочисленное значение типа long.

## <a name="syntax"></a>Синтаксис

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*стрсаурце*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*ендптр*<br/>
Указатель на символ, который останавливает сканирование.

*base*<br/>
Используемое числовое основание.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**стртол** возвращает значение, представленное в строке *стрсаурце*, за исключением случаев, когда представление вызовет переполнение, в этом случае возвращается **LONG_MAX** или **LONG_MIN**. **стртол** возвращает 0, если преобразование не может быть выполнено. **wcstol** возвращает значения по аналогии с **стртол**. Для обеих **функций в случае** переполнения или потери значимости устанавливается значение **ERANGE** .

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **стртол** преобразует *стрсаурце* в **Long**. **стртол** прекращает чтение строки *стрсаурце* на первом символе, который он не может распознать как часть числа. Это может быть завершающий нуль символ или первый числовой символ, который больше или равен *base*.

**wcstol** — это версия **стртол**для расширенных символов; его аргумент *стрсаурце* является строкой расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

Параметр категории **LC_NUMERIC** текущего языкового стандарта определяет распознавание символа системы счисления в *стрсаурце*; Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции без суффикса **_l** используют текущий языковой стандарт. **_strtol_l** и **_wcstol_l** идентичны соответствующим функциям без суффикса **_l** , за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *ендптр* не равно **null**, то указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *ендптр*. Если не удается выполнить преобразование (не найдены допустимые цифры или указана недопустимая база), значение *стрсаурце* хранится в расположении, на которое указывает *ендптр*.

**стртол** ждет, что *стрсаурце* указывает на строку следующего вида:

> [*пробел*] [{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [*цифры]* **-**

*Пробелы* могут состоять из пробелов и символов табуляции, которые игнорируются; *цифры* — это одна или несколько десятичных цифр; *буквы* являются одной или несколькими буквами от a до z (или от a до z).  Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение *base* равно от 2 до 36, то оно используется в качестве основания для числа. Если значение *base* равно 0, то для определения основания используются начальные символы строки, на которую указывает параметр *стрсаурце* . Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например, если *base* имеет значение 0, а первый проверенный символ — "0", то предполагается восьмеричное целое число, а символ "8" или "9" останавливает сканирование.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> или \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
