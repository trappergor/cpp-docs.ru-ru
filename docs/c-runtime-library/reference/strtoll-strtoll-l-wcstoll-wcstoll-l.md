---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l
ms.date: 4/2/2020
api_name:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
- _o__strtoll_l
- _o__wcstoll_l
- _o_strtoll
- _o_wcstoll
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d5a0ce8cb2c1d5f88d5439b99047609b32c8d2ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365180"
---
# <a name="strtoll-_strtoll_l-wcstoll-_wcstoll_l"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

Преобразует строку в **длинное** **длинное** значение.

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

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtoll** возвращает значение, представленное в строке *strSource,* за исключением случаев, когда представление может привести к переполнению, в этом случае он возвращает **LLONG_MAX** или **LLONG_MIN.** Функция возвращает 0, если преобразование не может быть выполнено. **wcstoll** возвращает значения аналогично **strtoll.**

**LLONG_MAX** и **LLONG_MIN** определены в LIMITS. H.

Если *strSource* **null** или *база* незероит и либо меньше, чем 2 или больше, чем 36, **errno** устанавливается на **EINVAL**.

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **strtoll** преобразует *strSource* в **длинный** **длинный.** Обе функции перестают читать строку *strSource* на первом символе, который они не могут распознать как часть числа. Это может быть прекращение нулевой характер, или это может быть первый числовой символ, который больше или равна *базе*. **wcstoll** является широкохарактерным вариантом **strtoll**; его *аргумент strSource* является широкохарактерной строкой. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Настройка **LC_NUMERIC** категории локализов определяет распознавание символа радикса в *strSource;* для получения дополнительной информации, [см setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, которые не имеют **_l** суффикса использовать текущий локали; **_strtoll_l** и **_wcstoll_l** идентичны соответствующим функциям, которые не имеют суффикса, за исключением того, что они вместо этого используют место, которое передается. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **является NULL,** указатель на символ, который остановил сканирование, хранится в месте, которое указывается *endptr.* Если конверсия не выполняется (не найдено действительных цифр или указана недействительная база), значение *strSource* хранится в месте, указанном *endptr.*

**strtoll** ожидает *strSource* указать на строку из следующей формы:

> -*белое пространство* -**+** &#124;) **-** **0** х **х** &#124; **X** х » - цифры &#124;*буквы.* *letters*

*Белое пространство* может состоять из символов пространства и вкладок, которые игнорируются; *цифры* являются одной или нескольких десятичных цифр; *буквы* являются одной или нескольких букв 'a' через 'z' (или 'A' через 'я'). Первый символ, который не соответствует этой форме, останавливает сканирование. Если *база* составляет от 2 до 36, то она используется в качестве основы числа. Если *основание* 0, для определения базы используются начальные символы строки, на которые указывает *strSource.* Если первый символ — 0, а второй символ не равен x или X, строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "а" до "z" (или от "А" до "Z") присваиваются значения от 10 до 35; допускаются только буквы с присвоенными значениями меньше *base*. Первый символ за пределами диапазона основания останавливает сканирование. Например, если *основание* равен 0 и сканируется первый символ '0', предполагается октальное число, и символ '8' или '9' останавливает сканирование.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtoll**, **_strtoll_l**|\<stdlib.h>|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
