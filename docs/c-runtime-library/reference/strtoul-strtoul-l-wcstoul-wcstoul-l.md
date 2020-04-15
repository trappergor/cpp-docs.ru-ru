---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l
ms.date: 4/2/2020
api_name:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
- _o__strtoul_l
- _o__wcstoul_l
- _o_strtoul
- _o_wcstoul
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strtoul
- _tcstoul
- wcstoul
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
ms.openlocfilehash: 60ae432fb11c5a29da2c4830c2a85305c6eaa46c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365617"
---
# <a name="strtoul-_strtoul_l-wcstoul-_wcstoul_l"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l

Преобразует строки в длинное целое число без знака.

## <a name="syntax"></a>Синтаксис

```C
unsigned long strtoul(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long _strtoul_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long wcstoul(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long _wcstoul_l(
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

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtoul** возвращает преобразованное значение, если такого имеется, или **ULONG_MAX** на переполнение. **strtoul** возвращает 0, если преобразование не может быть выполнено. **wcstoul** возвращает значения аналогично **strtoul.** Для обеих функций, **errno** устанавливается **на ERANGE,** если происходит переполнение или недопогабаритный поток.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Remarks

Каждая из этих функций преобразует строку ввода *strSource* в **неподписанный** **длинный.**

**strtoul** перестает читать строку *strSource* на первом символе он не может распознать как часть числа. Это может быть прекращение нулевой характер, или это может быть первый числовой символ больше или равна *базе*. Настройка **LC_NUMERIC** категории локализовать определяет распознавание символа радикса в *strSource*; для получения дополнительной информации [см.](setlocale-wsetlocale.md) **strtoul** и **wcstoul** используют текущий локализ; **_strtoul_l** и **_wcstoul_l** идентичны, за исключением того, что они используют местность, пройденую вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **является NULL,** указатель на символ, который остановил сканирование хранится в месте, указал на *endptr*. Если преобразование не выполняется (не было найдено действительных цифр или указана недействительная база), значение *strSource* хранится в месте, указанном *endptr.*

**wcstoul** является широкохарактерным вариантом **strtoul**; его *аргумент strSource* является широкохарактерной строкой. В остальном эти функции работают одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul** ожидает *strSource* указать на строку из следующей формы:

> -*белое пространство* -**+** &#124;) **-** **0** х **х** &#124; **X** х » - цифры &#124;*буквы.* *letters*

*Белое пространство* может состоять из символов пространства и вкладок, которые игнорируются. *цифры* являются одной или нескольких десятичных цифр. *буквы* являются одной или нескольких букв 'a' через 'z' (или 'A' через 'я'). Первый символ, который не соответствует этой форме, останавливает сканирование. Если *база* составляет от 2 до 36, то она используется в качестве основы числа. Если *основание* 0, начальные символы строки, на которые указывает *strSource,* используются для определения базы. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например, если *основание* равен 0 и первый отсканированный символ '0', предполагается октальное число, и символ '8' или '9' остановит сканирование. **strtoul** позволяет плюс**+**()**-** или минус () приставку знака; ведущий знак минус указывает на то, что значение возврата сведено на нет.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtoul**|\<stdlib.h>|
|**wcstoul**|\<stdlib.h> или \<wchar.h>|
|**_strtoul_l**|\<stdlib.h>|
|**_wcstoul_l**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
