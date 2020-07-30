---
title: ':::no-loc(setlocale):::, :::no-loc(_wsetlocale):::'
description: 'Описывает функции библиотеки среды выполнения Microsoft C (CRT) :::no-loc(setlocale)::: и :::no-loc(_wsetlocale)::: .'
ms.date: 4/2/2020
api_name:
- ':::no-loc(_wsetlocale):::'
- ':::no-loc(setlocale):::'
- '_o_:::no-loc(_wsetlocale):::'
- '_o_:::no-loc(setlocale):::'
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ':::no-loc(_wsetlocale):::'
- '_t:::no-loc(setlocale):::'
- ':::no-loc(setlocale):::'
helpviewer_keywords:
- 'w:::no-loc(setlocale)::: function'
- ':::no-loc(setlocale)::: function'
- 't:::no-loc(setlocale)::: function'
- locales, defining
- '_t:::no-loc(setlocale)::: function'
- defining locales
- ':::no-loc(_wsetlocale)::: function'
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- ':::no-loc(setlocale):::'
- ':::no-loc(_wsetlocale):::'
ms.openlocfilehash: 05e4e96297e2237ed6768e05ff4cacfd63744e1a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226142"
---
# <a name="no-locsetlocale-no-loc_wsetlocale"></a>:::no-loc(setlocale):::, :::no-loc(_wsetlocale):::

Устанавливает или извлекает языковой стандарт времени выполнения.

## <a name="syntax"></a>Синтаксис

```C
char *:::no-loc(setlocale):::(
   int category,
   const char *locale
);
wchar_t *:::no-loc(_wsetlocale):::(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Параметры

*категори*\
Категория, на которую влияет языковой стандарт.

*языкового стандарта*\
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если заданы допустимые *язык и региональные параметры* и *Категория* , возвращает указатель на строку, связанную с заданным *языковым стандартом* и *категорией*. Если *языковой стандарт* или *Категория* недействительна, возвращает пустой указатель, а текущие параметры языкового стандарта программы не изменяются.

Например, вызов

```C
:::no-loc(setlocale):::( LC_ALL, "en-US" );
```

задает все категории, возвращая только строку

```Output
en-US
```

Вы можете скопировать строку, возвращенную, **:::no-loc(setlocale):::** для восстановления этой части информации о языковых стандартах программы. Глобальное или локальное хранилище потока используется для строки, возвращаемой методом **:::no-loc(setlocale):::** . Последующие вызовы для **:::no-loc(setlocale):::** перезаписи строки, что делает недействительными указатели строк, возвращаемые предыдущими вызовами.

## <a name="remarks"></a>Remarks

Используйте **:::no-loc(setlocale):::** функцию, чтобы задать, изменить или запросить некоторые или все сведения о языковом стандарте текущей программы, указанные в параметрах *locale* и *Category*. *языковой стандарт* — это локальность (страна, регион и язык), для которой можно настроить определенные аспекты программы. К некоторым категориям, зависящим от языкового стандарта, относится формат дат и отображения денежных значений. Если для языкового *стандарта* задана строка по умолчанию для языка с несколькими формами, поддерживаемыми на компьютере, следует проверить **:::no-loc(setlocale):::** возвращаемое значение, чтобы узнать, какой язык действует. Например, если задать для параметра *locale* значение "Китайский", то возвращаемым значением может быть "китайский-упрощенный" или "Китайский (традиционное письмо)".

**:::no-loc(_wsetlocale):::**— Это версия с расширенными символами **:::no-loc(setlocale):::** ; аргумент *локали* и возвращаемое значение **:::no-loc(_wsetlocale):::** являются строками расширенных символов. **:::no-loc(_wsetlocale):::****:::no-loc(setlocale):::** поведение и идентично в противном случае.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_t:::no-loc(setlocale):::**|**:::no-loc(setlocale):::**|**:::no-loc(setlocale):::**|**:::no-loc(_wsetlocale):::**|

Аргумент *Category* определяет части информации о языковом стандарте программы, которые затрагиваются. Макросы, используемые для *категории* и части программы, на которые они влияют, выглядят следующим образом:

|флаг *категории*|Область применения|
|-|-|
| **LC_ALL** | Все категории, перечисленные ниже. |
| **LC_COLLATE** | Функции **strcoll**, **_stricoll**, **вксколл**, **_wcsicoll**, **стрксфрм**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**и **вксксфрм** . |
| **LC_CTYPE** | Функции обработки символов (кроме **знаков** **isxdigit**, **функции mbstowcs**и **mbtowc**, которые не затрагиваются). |
| **LC_MONETARY** | Сведения о денежном форматировании, возвращаемые функцией **localeconv** . |
| **LC_NUMERIC** | Символ десятичной запятой для отформатированных выходных подпрограмм (например, **printf**), для подпрограмм преобразования данных и для сведений о неденежном форматировании, возвращаемых функцией **localeconv**. В дополнение к символу десятичной запятой, **LC_NUMERIC** задает разделитель групп разрядов и строку управления группированием, возвращаемую функцией [localeconv](localeconv.md). |
| **LC_TIME** | Функции **strftime** и **wcsftime** . |

Эта функция проверяет параметр категории. Если параметр category не является одним из значений, указанных в предыдущей таблице, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **функция устанавливает** значение **Еинвал** и возвращает **null**.

Аргумент *locale* является указателем на строку, указывающую языковой стандарт. Дополнительные сведения о формате аргумента *языкового стандарта* см. в разделе [языковые имена, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Если аргумент *locale* указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией. Значение **C** указывает МИНИМАЛЬную стандартную среду ANSI для перевода C. Язык **C** предполагает, что все **`char`** типы данных имеют размер 1 байт, а их значение всегда меньше 256.

При запуске программы выполняется эквивалент следующего оператора:

`:::no-loc(setlocale):::( LC_ALL, "C" );`

Аргумент *locale* может принимать имя локали, строку языка, языковую строку и код страны или региона, кодовую страницу, языковую строку, код страны или региона и кодовую страницу. Набор доступных имен языковых стандартов, языков, кодов стран и регионов, а также кодовых страниц включает все поддерживаемые API NLS Windows. Набор имен языковых стандартов, поддерживаемых, **:::no-loc(setlocale):::** описывается в разделе [имена языков, языков и строк страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строк языка и страны или региона, поддерживаемых в, **:::no-loc(setlocale):::** указан в [строках языка](../../c-runtime-library/language-strings.md) и [строках страны или региона](../../c-runtime-library/country-region-strings.md). Рекомендуется использовать форму имени языкового стандарта для обеспечения производительности и удобства поддержки строк языкового стандарта, внедренных в код или сериализованных в хранилище. Строковые значения имен языкового стандарта реже подвергаются изменению обновлением операционной системы, чем язык и форма названия страны или региона.

Указатель null, который передается в качестве аргумента *локали* , указывает **:::no-loc(setlocale):::** на запрос, а не на установку международного окружения. Если аргумент *locale* является пустым указателем, текущее значение языкового стандарта программы не меняется. Вместо этого **:::no-loc(setlocale):::** возвращает указатель на строку, связанную с *категорией* текущего языкового стандарта потока. Если аргумент *Category* имеет значение **LC_ALL**, функция возвращает строку, которая указывает текущее значение каждой категории, разделенные точкой с запятой. Например, последовательность вызовов

```C
// Set all categories and return "en-US"
:::no-loc(setlocale):::(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
:::no-loc(setlocale):::(LC_MONETARY, "fr-FR");
printf("%s\n", :::no-loc(setlocale):::(LC_ALL, NULL));
```

возвращает

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

Строка, связанная с категорией **LC_ALL** .

Следующие примеры относятся к категории **LC_ALL** . Любая из строк ". OCP "и". ACP» можно использовать вместо номера кодовой страницы для указания использования пользовательской кодовой страницы OEM по умолчанию и кодовой страницы ANSI по умолчанию для этого имени языкового стандарта соответственно.

- `:::no-loc(setlocale):::( LC_ALL, "" );`

   Задает языковой стандарт по умолчанию, т.е. заданную по умолчанию для пользователя кодовую страницу ANSI, полученную от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается значением, возвращаемым функцией [жетакп](/windows/win32/api/winnls/nf-winnls-getacp).

- `:::no-loc(setlocale):::( LC_ALL, ".OCP" );`

   Задает языковой стандарт для текущей кодовой страницы OEM, полученной от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается в качестве значения [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) для имени локали пользователя по умолчанию по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `:::no-loc(setlocale):::( LC_ALL, ".ACP" );`

   Задает языковой стандарт согласно текущей кодовой странице ANSI, полученной от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для имени локали пользователя по умолчанию по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `:::no-loc(setlocale):::( LC_ALL, "<localename>" );`

   Задает языковой стандарт для имени языкового стандарта, указанного в *\<localename>* . Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для указанного имени локали по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `:::no-loc(setlocale):::( LC_ALL, "<language>_<country>" );`

   Задает языковой стандарт и страну или регион, указанные в параметре *\<language>* и, а также *\<country>* кодовую страницу по умолчанию, полученную из операционной системы узла. Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для указанного имени локали по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `:::no-loc(setlocale):::( LC_ALL, "<language>_<country>.<code_page>" );`

   Задает языковой стандарт для языка, страны или региона, а также кодовую страницу, определяемую *\<language>* *\<country>* *\<code_page>* строками, и. Можно использовать различные сочетания языка, страны или региона и кодовой страницы. Например, этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей 1252.

   `:::no-loc(setlocale):::( LC_ALL, "French_Canada.1252" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию ANSI.

   `:::no-loc(setlocale):::( LC_ALL, "French_Canada.ACP" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию OEM.

   `:::no-loc(setlocale):::( LC_ALL, "French_Canada.OCP" );`

- `:::no-loc(setlocale):::( LC_ALL, "<language>" );`

   Устанавливает языковой стандарт для языка, указанного в параметре *\<language>* , и использует страну или регион по умолчанию для указанного языка и кодовую страницу пользователя по умолчанию ANSI для этой страны или региона, полученную из операционной системы узла. Например, следующие вызовы **:::no-loc(setlocale):::** функционально эквивалентны:

   `:::no-loc(setlocale):::( LC_ALL, "en-US" );`

   `:::no-loc(setlocale):::( LC_ALL, "English" );`

   `:::no-loc(setlocale):::( LC_ALL, "English_United States.1252" );`

   Рекомендуется использовать первую форму для обеспечения производительности и простоты обслуживания.

- `:::no-loc(setlocale):::( LC_ALL, ".<code_page>" );`

   Задает кодовую страницу согласно значению, отображаемому *<code_page>*, вместе с языком и страной или регионом по умолчанию (согласно определению операционной системы) для заданной кодовой страницы.

Для изменения кодовой страницы категория должна быть либо **LC_ALL** , либо **LC_CTYPE** . Например, если страна или регион по умолчанию и язык операционной системы узла имеют значение "США" и "Английский", следующие два вызова **:::no-loc(setlocale):::** функционально эквивалентны:

`:::no-loc(setlocale):::( LC_ALL, ".1252" );`

`:::no-loc(setlocale):::( LC_ALL, "English_United States.1252");`

Дополнительные сведения см. в описании [:::no-loc(setlocale):::](../../preprocessor/:::no-loc(setlocale):::.md) директивы pragma в [справочнике по препроцессору C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).

Функция [_configthreadlocale](configthreadlocale.md) используется для управления **:::no-loc(setlocale):::** тем, влияет ли на языковой стандарт для всех потоков в программе или только на языковой стандарт вызывающего потока.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**:::no-loc(setlocale):::**|\<locale.h>|
|**:::no-loc(_wsetlocale):::**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_:::no-loc(setlocale):::.c
//
// This program demonstrates the use of :::no-loc(setlocale)::: when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           :::no-loc(setlocale):::(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           :::no-loc(setlocale):::(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>См. также раздел

[Имена языковых стандартов, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[Языкового стандарта](../../c-runtime-library/locale.md)\
[localeconv](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[функции mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[стрксфрм, вксксфрм, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
