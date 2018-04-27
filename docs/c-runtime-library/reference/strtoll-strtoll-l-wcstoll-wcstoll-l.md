---
title: Функции strtoll, _strtoll_l, wcstoll, _wcstoll_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
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
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
dev_langs:
- C++
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9138ec6a298c302446077a2c071aef659c9a0ccb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="strtoll-strtolll-wcstoll-wcstolll"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

Преобразует строку в **длинные** **длинные** значение.

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

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*base*<br/>
Используемое числовое основание.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtoll** возвращает значение, представленное в строке *strSource*, за исключением случаев, когда представление вызвало бы переполнение — в этом случае он возвращает **LLONG_MAX** или **LLONG_MIN**. Функция возвращает 0, если преобразование не может быть выполнено. **wcstoll** возвращает значения в аналогично **strtoll**.

**LLONG_MAX** и **LLONG_MIN** определяются в пределах. З.

Если *strSource* — **NULL** или *базового* отлично от нуля и либо меньше 2 или больше, чем 36, **errno** равно **EINVAL** .

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Strtoll** функция преобразует *strSource* для **длинные** **длинные**. Обе функции прекратить чтение строки *strSource* с первого символа, они не может распознать как часть числа. Это может быть конечный нуль-символ или первый числовой символ, который больше или равно часто бывает *базового*. **wcstoll** — это двухбайтовая версия **strtoll**; его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции работают одинаково.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Языкового стандарта **LC_NUMERIC** параметра категории определяет распознавание символа системы счисления в *strSource*; Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, которые не имеют **_l** суффикс используют текущий языковой стандарт; **_strtoll_l** и **_wcstoll_l** идентичны соответствующим функциям, у которых нет суффикса, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который остановлена сканирования хранится в расположении, которое указывает *endptr*. Если преобразование не может быть выполнена (не найдены допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, которое указывает *endptr*.

**strtoll** ожидает *strSource* на строку следующего вида:

> [*пробелов*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*цифр* &#124; *буквы*]  

Объект *пробелов* может состоять из пробелов и символов табуляции, которые игнорируются. *цифр* — один или несколько десятичных цифр; *буквы* — это один или несколько букв «» до «z» (или «A» до «Z»). Первый символ, который не соответствует этой форме, останавливает сканирование. Если *базового* — от 2 до 36, то он используется как основание системы счисления. Если *базового* равно 0, начальных символов строки, который указывает *strSource* используются для определения основания. Если первый символ — 0, а второй символ не равен x или X, строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например если *базового* равно 0 и первый считанный символ — "0", предполагается восьмеричное целое число и символ "8" или "9" останавливает проверку.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtoll**, **_strtoll_l**|\<stdlib.h>|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h> или \<wchar.h>|

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
