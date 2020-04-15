---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 4/2/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- _o__strtol_l
- _o__wcstol_l
- _o_strtol
- _o_wcstol
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
ms.openlocfilehash: dbeaf04d34aa20e15de48e99082ed07edb6129ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320476"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Преобразуйте строки в **длинное** значение целых.

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

*Строка*\
Строка, завершающаяся символом NULL, для преобразования.

*end_ptr*\
Параметр вывода, установленный для того, чтобы указать на символ после последнего интерпретируемого персонажа. Игнорируется, если **NULL**.

*Базы*\
Используемое числовое основание.

*Языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtol,** **wcstol,** **_strtol_l**и **_wcstol_l** вернуть значение, представленное в *строке.* Они возвращаются 0, если преобразование невозможно. Когда представление может привести к переполнению, они **возвращаются LONG_MAX** или **LONG_MIN**.

**errno** устанавливается в **ERANGE,** если происходит переполнение или недопог. Это установлено на **EINVAL,** если *строка* **NULL**. Или, если *база* незероит и меньше, чем 2, или больше, чем 36. Для получения дополнительной информации о **ERANGE**, **EINVAL**, и другие коды возврата, см [_doserrno, errno, _sys_errlist, и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

**Strtol,** **wcstol,** **_strtol_l,** и **_wcstol_l** функции преобразуют *строку* в **длинную.** Они перестают читать *строку* при первом персонаже, не признанном частью числа. Это может быть термин прекращения-нулевой, или первый алфавитный символ больше или равна *базе.*

**wcstol** и **_wcstol_l** являются широкохарактерными версиями **снтола** и **_strtol_l.** Их *строка* аргумент широкого характера строки. Эти функции ведут себя одинаково, чтобы **strtol** и **_strtol_l** в противном случае. Настройка **LC_NUMERIC** категории локали определяет распознавание символа радикса (дробный маркер или десятичная точка) в *строке.* Функции **strtol** и **wcstol** используют текущий локал. **_strtol_l** и **_wcstol_l** использовать местность, принятую вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md)

Когда *end_ptr* **NULL,** он игнорируется. В противном случае указатель на символ, остановивший сканирование, хранится в месте, на которое *указали end_ptr.* Преобразование невозможно, если не найдено действительных цифр или указана недействительная база. Значение *строки* затем хранится в месте, на который указывает *end_ptr.*

**strtol** *ожидает* строку, чтобы указать на строку из следующей формы:

> -*белое пространство* -**+** &#124;) **-** **0** х **х** &#124; **X** *alphanumerics*

Квадратные скобки ()`[ ]`окружают дополнительные элементы. Кудрявые скобки`{ | }`и вертикальная планка () окружают альтернативы для одного элемента. *белое пространство* может состоять из символов пространства и вкладок, которые игнорируются. *алфавитными* являются десятичные цифры или буквы "a" через 'z' (или 'A' через 'я'). Первый символ, который не соответствует этой форме, останавливает сканирование. Если *база* находится между 2 и 36, то она используется в качестве основы числа. Если *основание* 0, начальные символы строки, на которые указывает *строка строки* используются для определения базы. Если первый символ равен 0, а второй — не «x» или «X», строка интерпретируется как октальное целых. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквы 'a' через 'z' (или 'A' через 'я') присваиваются значениям от 10 до 35. Сканирование позволяет только буквы, значения которых меньше, чем *база.* Первый символ за пределами диапазона основания останавливает сканирование. Например, предположим, *строка* начинается с "01". Если *основание* 0, сканер предполагает, что это октальное число. Персонаж '8' или '9' останавливает сканирование.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

**_strtol_l** Функции **_wcstol_l** и функции microsoft специфичны, а не являются частью библиотеки Standard C. Дополнительные сведения о совместимости см. в статье [Compatibility](../compatibility.md).

## <a name="example"></a>Пример

Смотрите пример [strtod](strtod-strtod-l-wcstod-wcstod-l.md)для .

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../data-conversion.md)\
[Языкового стандарта](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Строка к функциям численного значения](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
