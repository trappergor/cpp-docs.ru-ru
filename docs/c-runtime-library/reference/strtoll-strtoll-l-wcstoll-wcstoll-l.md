---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l
ms.date: 11/04/2016
api_name:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
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
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
ms.openlocfilehash: 152efb26f0a2e9a312654e37a95bee15f386aa9f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946440"
---
# <a name="strtoll-_strtoll_l-wcstoll-_wcstoll_l"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

Преобразует строку в **длинное** **значение типа** Long.

## <a name="syntax"></a>Синтаксис

```C
long long strtoll(
   const char *strSource,
   char **endptr,
   int base
);
long long wcstoll(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long long _strtoll_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long long _wcstoll_l(
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

**стртолл** возвращает значение, представленное в строке *стрсаурце*, за исключением случаев, когда представление вызовет переполнение — в этом случае возвращается **LLONG_MAX** или **LLONG_MIN**. Функция возвращает 0, если преобразование не может быть выполнено. **вкстолл** возвращает значения по аналогии с **стртолл**.

**LLONG_MAX** и **LLONG_MIN** определяются в ограничениях. Высоты.

Если *стрсаурце* имеет **значение NULL** или *база* не имеет значения, равного нулю и меньше 2 или больше **36, то** для параметра «значение передается **еинвал**».

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **стртолл** преобразует *стрсаурце* в **длинный** **Формат**Long. Обе функции прекращают чтение строки *стрсаурце* на первом символе, который они не могут распознать как часть числа. Это может быть завершающий нуль символ или первый числовой символ, который больше или равен *base*. **вкстолл** — это версия **стртолл**для расширенных символов; его аргумент *стрсаурце* является строкой расширенных символов. В остальном эти функции работают одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Параметр **LC_NUMERIC** Category (языковой стандарт) определяет распознавание символа основания системы счисления в *стрсаурце*; Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, у которых нет суффикса **_l** , используют текущий языковой стандарт. **_strtoll_l** и **_wcstoll_l** идентичны соответствующим функциям, у которых нет суффикса, за исключением того, что они вместо этого используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *ендптр* не равно **null**, то указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *ендптр*. Если не удается выполнить преобразование (не найдены допустимые цифры или указана недопустимая база), значение *стрсаурце* хранится в расположении, на которое указывает *ендптр*.

**стртолл** ждет, что *стрсаурце* указывает на строку следующего вида:

> [*пробел*] [{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [*цифры]* **-**

*Пробелы* могут состоять из пробелов и символов табуляции, которые игнорируются; *цифры* — это одна или несколько десятичных цифр; *буквы* являются одной или несколькими буквами от a до z (или от a до z). Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение *base* равно от 2 до 36, то оно используется в качестве основания для числа. Если значение *base* равно 0, то для определения базы используются начальные символы строки, на которую указывает *стрсаурце* . Если первый символ — 0, а второй символ не равен x или X, строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например, если *base* имеет значение 0, а первый проверенный символ — "0", то предполагается восьмеричное целое число, а символ "8" или "9" останавливает сканирование.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**стртолл**, **_strtoll_l**|\<stdlib.h>|
|**вкстолл**, **_wcstoll_l**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
