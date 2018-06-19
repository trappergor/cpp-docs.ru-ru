---
title: _create_locale, _wcreate_locale | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9be41a2d156a522c74349c3457295502ae6d4f43
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451944"
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale

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

*category*<br/>
Категория.

*locale*<br/>
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если допустимый *языкового стандарта* и *категории* заданы, возвращает параметры указанный языковой стандарт как **_locale_t** объекта. Текущие параметры языкового стандарта программы не изменяются.

## <a name="remarks"></a>Примечания

**_Create_locale** функция позволяет создать объект, представляющий определенные параметры конкретного региона, для использования в версии языкового стандарта много функций CRT (функции с **_l** суффикс ). Поведение аналогично поведению **setlocale**, за исключением того, что вместо применения параметров указанного языкового стандарта в текущей среде, параметры сохраняются в **_locale_t** структуру, которая возвращается. **_Locale_t** структуры следует освободить с помощью [_free_locale](free-locale.md) когда он больше не нужен.

**_wcreate_locale** — это двухбайтовая версия **_create_locale**; *языкового стандарта* аргумент **_wcreate_locale** представляет собой строку расширенных символов. **_wcreate_locale** и **_create_locale** ведут себя идентично.

*Категории* аргумент указывает части поведение языкового стандарта, затрагиваемые. Флаги, используемые для *категории* и части программы, они влияют на, как показано в следующей таблице.

|*Категория* флаг|Затрагивает|
|-|-|
**LC_ALL**|Все категории, перечисленные ниже.
**LC_COLLATE**|**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_ strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, и **wcsxfrm** функции.
**LC_CTYPE**|Функции обработки символов (за исключением **isdigit**, **isxdigit**, **mbstowcs**, и **mbtowc**, которые не затрагиваются).
**LC_MONETARY**|Форматирование денежных информацию, возвращаемую **localeconv** функции.
**LC_NUMERIC**|Символ для процедур форматированного вывода десятичной запятой (например, **printf**), для процедур преобразования данных и не относящихся к денежным форматирования сведения, возвращенные **localeconv**. Помимо символа десятичного разделителя **LC_NUMERIC** задает разделитель тысяч и группирование управления строку, возвращаемую [localeconv](localeconv.md).
**LC_TIME**|**Strftime** и **wcsftime** функции.

Эта функция проверяет *категории* и *языкового стандарта* параметров. Если параметр категории не является одним из значений, расположенных в предыдущей таблице или *языкового стандарта* — **NULL**, функция возвращает **NULL**.

*Языкового стандарта* аргумент — указатель на строку, которая задает языковой стандарт. Сведения о формате параметра *языкового стандарта* аргумент, в разделе [имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).

*Языкового стандарта* аргумент может принимать имя языкового стандарта, строки с названием языка, строки с названием языка и код страны или региона, кодовую страницу или строку языка, код страны или региона и кодовой страницы. Набор доступных имен языкового стандарта, названий языков, кодов страны и кодовых страниц включает все поддерживаемые API многоязыковой поддержки Windows, кроме кодовых страниц, требующих более 2 байт на один знак, например UTF-7 и UTF-8. Если указать кодовую страницу как UTF-7 или UTF-8, **_create_locale** не удастся и возвращать **NULL**. Набор имен языковых стандартов, поддерживаемых **_create_locale** описаны в [имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строк языка и страны или региона, поддерживаемых **_create_locale** , перечислены в [строки языка](../../c-runtime-library/language-strings.md) и [стран и регионов](../../c-runtime-library/country-region-strings.md).

Дополнительные сведения о региональных параметрах см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Предыдущее имя этой функции **__create_locale** (с двух символов подчеркивания), рекомендуется к использованию.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Строки языка](../../c-runtime-library/language-strings.md)<br/>
[Строки страны и региона](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
