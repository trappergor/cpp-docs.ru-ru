---
title: _create_locale, _wcreate_locale
ms.date: 4/2/2020
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
- _o__create_locale
- _o__wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: 611eaf342776b9a0f57c4f55c52a841c3fd13fb5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348256"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

Создает объект языкового стандарта.

## <a name="syntax"></a>Синтаксис

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Параметры

*Категории*<br/>
Категория.

*Языкового стандарта*<br/>
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если указано действительное *место и* *категория,* возвращаетуказанные настройки локализации в качестве **_locale_t** объекта. Текущие параметры языкового стандарта программы не изменяются.

## <a name="remarks"></a>Remarks

Функция **_create_locale** позволяет создать объект, представляющий определенные параметры, характерные для конкретных регионов, для использования в конкретных версиях многих функций CRT (функции с **_l** суффиксом). Поведение аналогично **setlocale,** за исключением того, что вместо применения определенных параметров локальности к текущей среде настройки сохраняются в **_locale_t** структуре, которая возвращается. Структура **_locale_t** должна быть освобождена с помощью [_free_locale,](free-locale.md) когда она больше не нужна.

**_wcreate_locale** является широкохарактерным вариантом **_create_locale;** *аргумент локализовать* **_wcreate_locale** является широкохарактерной строкой. **_wcreate_locale** и **_create_locale** ведут себя одинаково иначе.

Аргумент *категории* определяет части поведения, конкретного локализации, которые затронуты. Флаги, используемые для *категории* и части программы, на которые они влияют, показаны в этой таблице:

| *флаг категории* | Область применения |
|-----------------|---------|
| **LC_ALL** |Все категории, перечисленные ниже. |
| **LC_COLLATE** |**Strcoll**, **_stricoll,** **wcscoll**, **_wcsicoll,** **strxfrm**, **_strncoll,** **_strnicoll,** **_wcsncoll,** **_wcsnicoll,** и **wcsxfrm** функции. |
| **LC_CTYPE** | Функции обработки символов (кроме **isdigit,** **isxdigit,** **mbstowcs**и **mbtowc**, которые не затрагиваются). |
| **LC_MONETARY** | Информация о денежно-кредитной форматировании, возвращаемые функцией **localeconv.** |
| **LC_NUMERIC** | Символ десятичной точки для отформатированных процедур вывода (таких как **printf),** для процедур преобразования данных, а также для неденежной информации форматирования, возвращенной **localeconv.** В дополнение к десятичной точке характер, **LC_NUMERIC** устанавливает тысячи сепараторов и группировки управления строки возвращается [localeconv](localeconv.md). |
| **LC_TIME** | Функции **strftime** и **wcsftime.** |

Эта функция проверяет параметры *категории* и *локализации.* Если параметр категории не является одним из значений, приведенных в предыдущей таблице, или если *локаль* **null,** функция возвращает **NULL.**

Аргумент *локализов* является указателем на строку, которая определяет локализует. Для получения информации о формате [Locale Names, Languages, and Country/Region Strings](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) *аргумента локализации* см.

Аргумент *локали* может принимать имя локали, языковую строку, языковую строку и код страны/региона, страницу кода или строку языка, код страны/региона и страницу кода. Набор доступных имен локализаций, языков, кодов стран/регионов и страниц кода включает в себя все, что поддерживается API Windows NLS. Набор имен локализуев, поддерживаемых **_create_locale,** описан в [языках, языках и строках страны/региона.](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) Набор языковых и страновых/регионанных строк, поддерживаемых **_create_locale,** указан в [языковых струнах](../../c-runtime-library/language-strings.md) и [строках страны/региона.](../../c-runtime-library/country-region-strings.md)

Дополнительные сведения о региональных параметрах см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Предыдущее название этой функции, **__create_locale** (с двумя ведущими подчеркнутыми), было униточено.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>См. также раздел

[Названия языков, языков и страновых/регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[строки страны и региона](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
