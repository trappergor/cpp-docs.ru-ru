---
title: strtoull, _strtoull_l, wcstoull, _wcstoull_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
dev_langs:
- C++
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d984dc88af4c4029c139d13cfa19a2c4159f4eab
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="strtoull-strtoulll-wcstoull-wcstoulll"></a>strtoull, _strtoull_l, wcstoull, _wcstoull_l

Преобразует строки в целое значение long long без знака.

## <a name="syntax"></a>Синтаксис

```C
unsigned long long strtoull(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long long _strtoull_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long long wcstoull(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long long _wcstoull_l(
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

**strtoull** возвращает преобразованное значение, если он существует, или **ULLONG_MAX** в случае переполнения. **strtoull** возвращает 0, если преобразование не может быть выполнена. **wcstoull** возвращает значения в аналогично **strtoull**. Для обеих функций **errno** равно **ERANGE** при возникновении переполнения или потери точности.

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций преобразует входную строку *strSource* для **неподписанные** **длинные** **длинные** целочисленное значение.

**strtoull** прекращает чтение строки *strSource* с первого символа, не удается распознать как часть числа. Это может быть конечный нуль-символ или первый числовой символ, который больше или равно часто бывает *базового*. Параметр **LC_NUMERIC** категории языкового стандарта определяет распознавание символа системы счисления в *strSource*; Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). **strtoull** и **wcstoull** используют текущий языковой стандарт; **_strtoull_l** и **_wcstoull_l** вместо в противном случае используйте языкового стандарта, который передается в, но являются идентичными. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **NULL**, указатель на символ, который остановлена сканирования хранится в расположении, которое указывает *endptr*. Если преобразование не может быть выполнена (не найдены допустимые цифры или указано недопустимое основание), значение *strSource* хранится в расположении, которое указывает *endptr*.

**wcstoull** — это двухбайтовая версия **strtoull** и его *strSource* аргумент представляет собой строку расширенных символов. В остальном эти функции работают одинаково.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoull**|**strtoull**|**strtoull**|**wcstoull**|
|**_tcstoull_l**|**strtoull_l**|**_strtoull_l**|**_wcstoull_l**|

**strtoull** ожидает *strSource* на строку следующего вида:

> [*пробелов*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*цифр* &#124; *буквы*]  

Объект *пробелов* может состоять из пробелов и символов табуляции, которые игнорируются. *цифры* — один или несколько десятичных цифр. *буквы* — это один или несколько букв «» до «z» (или «A» до «Z»). Первый символ, который не соответствует этой форме, останавливает сканирование. Если *базового* — от 2 до 36, то он используется как основание системы счисления. Если *базового* равно 0, начальных символов строки, который указывает *strSource* используются для определения основания. Если первый символ — 0, а второй символ не равен x или X, строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например если *базового* равно 0 и первый считанный символ — "0", предполагается восьмеричное целое число и символ "8" или "9" останавливает проверку. **strtoull** позволяет знак плюс (**+**) или «минус» (**-**) префикс; начальные отрицательный знак указывает, что возвращаемое значение будет инвертировано.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtoull**|\<stdlib.h>|
|**wcstoull**|\<stdlib.h> или \<wchar.h>|
|**_strtoull_l**|\<stdlib.h>|
|**_wcstoull_l**|\<stdlib.h> или \<wchar.h>|

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
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
