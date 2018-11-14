---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 11/04/2016
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
ms.openlocfilehash: 73df5dd3ffcd4a9b2fca8b6b713b645ef94addb5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326723"
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol, wcstol, _strtol_l, _wcstol_l

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

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*base*<br/>
Используемое числовое основание.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**функции strtol** возвращает значение, представленное в строке *strSource*, кроме случаев, когда представление вызвало бы переполнение, в этом случае он возвращает **LONG_MAX** или **LONG_ MIN**. **функции strtol** возвращает 0, если преобразование не может быть выполнено. **wcstol** возвращает значения аналогично функции **strtol**. Для обеих функций **errno** присваивается **ERANGE** при возникновении переполнения или потери значимости.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Strtol** функция преобразует *strSource* для **long**. **функции strtol** прекращает чтение строки *strSource* на первом знаке, она не может распознать как часть числа. Это может быть завершающий нуль-символ, или он может быть первый числовой символ больше или равно *базового*.

**wcstol** — это двухбайтовая версия **strtol**; его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

Текущего языкового стандарта **LC_NUMERIC** параметр category определяет распознавание символа основания системы счисления в *strSource*; Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции, не имеющие **_l** суффикс используют текущий языковой стандарт; **_strtol_l** и **_wcstol_l** идентичны соответствующим функциям без **_l** суффикса, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который останавливает сканирование, хранится в расположении, указанном *endptr*. Если преобразование не может быть выполнено (найдены нет допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, указанном *endptr*.

**функции strtol** ожидает *strSource* указывает строку следующего вида:

> [*пробелы*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*цифр* &#124; *буквы*]  

Объект *пробелы* может состоять из пробелов и символов табуляции, которые игнорируются; *цифр* — один или несколько десятичных цифр; *буквы* имеют один или несколько букв «» до «z» (или «A» до «Z»).  Первый символ, который не соответствует этой форме, останавливает сканирование. Если *базового* — от 2 до 36, то он используется как основание системы счисления. Если *базового* равно 0, то начальные символы строки, на которые указывают *strSource* используются для определения основания. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например если *базового* 0 и первый считанный символ — "0", предполагается восьмеричное целое число и символ "8" или "9" остановит сканирование.

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
