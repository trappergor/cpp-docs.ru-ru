---
title: setlocale, _wsetlocale
description: Описывает функции setlocale библиотеки Microsoft C runtime (CRT) и _wsetlocale.
ms.date: 4/2/2020
api_name:
- _wsetlocale
- setlocale
- _o__wsetlocale
- _o_setlocale
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
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- setlocale
- _wsetlocale
ms.openlocfilehash: 2834229839153c3154caadf71e5fb30d84ed2f1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353713"
---
# <a name="setlocale-_wsetlocale"></a>setlocale, _wsetlocale

Устанавливает или извлекает языковой стандарт времени выполнения.

## <a name="syntax"></a>Синтаксис

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Параметры

*Категории*\
Категория, на которую влияет языковой стандарт.

*Языкового стандарта*\
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если дан действительный *локаль* и *категория,* возвращаетуказатель строки, связанной с указанным *локалью* и *категорией.* Если *локализуется* или *категория,* возвращается указатель нулевой орилин, а текущие настройки локальности программы остаются неизменными.

Например, вызов

```C
setlocale( LC_ALL, "en-US" );
```

задает все категории, возвращая только строку

```Output
en-US
```

Вы можете скопировать строку, возвращенную **setlocale,** чтобы восстановить эту часть информации о локализации программы. Глобальное или локальное хранилище потоков используется для строки, возвращенной **setlocale.** Позже вызовы **для установки** перезаписи строки, которая аннулирует строки указатели, возвращенные более ранними вызовами.

## <a name="remarks"></a>Remarks

Используйте функцию **setlocale** для установки, изменения или запроса некоторой или всей текущей информации о локальном потоке программы, указанной *в местности* и *категории.* *локализуются* к местности (страна/регион и язык), для которой вы можете настроить определенные аспекты вашей программы. К некоторым категориям, зависящим от языкового стандарта, относится формат дат и отображения денежных значений. Если вы *установите язык по* умолчанию для языка, который имеет несколько форм, поддерживаемых на вашем компьютере, следует проверить значение возврата **setlocale,** чтобы увидеть, какой язык действует. Например, если вы установите *язык* на "китайский" возврат новое значение может быть либо "китайско-упрощенным", либо "китайско-традиционным".

**_wsetlocale** является широкохарактерной версией **setlocale;** *аргумент апогея* и значение возврата **_wsetlocale** являются широкохарактерными строками. **_wsetlocale** и **setlocale** ведут себя одинаково иначе.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

Аргумент *категории* определяет части информации о локальном сообщении программы, которые затронуты. Макросы, используемые для *категории,* и части программы, на которые они влияют, следующие:

|*флаг категории*|Область применения|
|-|-|
| **LC_ALL** | Все категории, перечисленные ниже. |
| **LC_COLLATE** | **Strcoll**, **_stricoll,** **wcscoll**, **_wcsicoll,** **strxfrm**, **_strncoll,** **_strnicoll,** **_wcsncoll,** **_wcsnicoll,** и **wcsxfrm** функции. |
| **LC_CTYPE** | Функции обработки символов (кроме **isdigit,** **isxdigit,** **mbstowcs**и **mbtowc**, которые не затрагиваются). |
| **LC_MONETARY** | Информация о денежно-кредитной форматировании, возвращаемые функцией **localeconv.** |
| **LC_NUMERIC** | Символ десятичной точки для отформатированных процедур вывода (таких как **printf),** для процедур преобразования данных, а также для неденежной информации форматирования, возвращенной **localeconv.** В дополнение к десятичной точке характер, **LC_NUMERIC** устанавливает тысячи сепараторов и группировки управления строки возвращается [localeconv](localeconv.md). |
| **LC_TIME** | Функции **strftime** и **wcsftime.** |

Эта функция проверяет параметр категории. Если параметр категории не является одним из значений, приведенных в предыдущей таблице, вызывается обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция устанавливает **errno** **к EINVAL** и возвращает **NULL**.

Аргумент *локализов* является указателем на строку, которая определяет локализует. Для получения информации о формате [Locale Names, Languages, and Country/Region Strings](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) *аргумента локализации* см. Если аргумент *locale* указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией. Значение **C** определяет минимальную среду соответствия ANSI для перевода C. **C** locale предполагает, что все типы данных **char** являются 1 байт и что их значение всегда меньше 256.

При запуске программы выполняется эквивалент следующего оператора:

`setlocale( LC_ALL, "C" );`

Аргумент *локали* может принимать имя локали, языковую строку, языковую строку и код страны/региона, страницу кода или строку языка, код страны/региона и страницу кода. Набор доступных имен локализаций, языков, кодов стран/регионов и страниц кода включает в себя все страницы, поддерживаемые API Windows NLS. Набор имен локаль, поддерживаемый **setlocale,** описан в [языках, языках и строках страны/региона.](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) Набор строк языка и стран/регионов, поддерживаемых **setlocale,** указан в [языковых строках](../../c-runtime-library/language-strings.md) и [строках страны/региона.](../../c-runtime-library/country-region-strings.md) Рекомендуется использовать форму имени языкового стандарта для обеспечения производительности и удобства поддержки строк языкового стандарта, внедренных в код или сериализованных в хранилище. Строковые значения имен языкового стандарта реже подвергаются изменению обновлением операционной системы, чем язык и форма названия страны или региона.

Нулевая указатель, который пройден, как аргумент *локала* говорит **setlocale** к запросу, а не для установки международной среды. Если аргумент *локализов* является нулевой указателем, текущая настройка локализации программы не изменяется. Вместо этого **setlocale** возвращает указатель на строку, связанную с *категорией* текущего локатора потока. Если аргумент *категории* **LC_ALL,** функция возвращает строку, которая указывает текущую настройку каждой категории, разделенную запятыми. Например, последовательность вызовов

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

возвращает

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

которая является строкой, связанной с категорией **LC_ALL.**

Следующие примеры относятся к категории **LC_ALL.** Любая из струн ". OCP" и ". ACP" может использоваться вместо номера страницы кода для указания использования страницы кода OEM-кода пользователя по умолчанию и страницы кода ANSI пользователя по умолчанию для этого имени локали, соответственно.

- `setlocale( LC_ALL, "" );`

   Задает языковой стандарт по умолчанию, т.е. заданную по умолчанию для пользователя кодовую страницу ANSI, полученную от операционной системы. Имя ломык устанавливается к значению, возвращенному [GetUserDefaultLocaleName.](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) Страница кода устанавливается на значение, возвращенное [GetACP.](/windows/win32/api/winnls/nf-winnls-getacp)

- `setlocale( LC_ALL, ".OCP" );`

   Устанавливает локаль на текущую страницу Кода OEM, полученную из операционной системы. Имя ломык устанавливается к значению, возвращенному [GetUserDefaultLocaleName.](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) Страница кода устанавливается на [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) значение для имени локального пользователя по умолчанию [от GetLocaleInfoEx.](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)

- `setlocale( LC_ALL, ".ACP" );`

   Задает языковой стандарт согласно текущей кодовой странице ANSI, полученной от операционной системы. Имя ломык устанавливается к значению, возвращенному [GetUserDefaultLocaleName.](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) Страница кода устанавливается на [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) значение для имени локального пользователя по умолчанию [от GetLocaleInfoEx.](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)

- `setlocale( LC_ALL, "<localename>" );`

   Устанавливает локализу на название ломы, указанное * \<>. * Страница кода устанавливается на [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) значение для указанного имени локализуем [GetLocaleInfoEx.](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)

- `setlocale( LC_ALL, "<language>_<country>" );`

   Устанавливает язык и страну/регион, указанный * \<>языка* и * \<>страны, *вместе со страницей кода по умолчанию, полученной из операционной системы хоста. Страница кода устанавливается на [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) значение для указанного имени локализуем [GetLocaleInfoEx.](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Устанавливает язык языка, страны/региона и страницы кода, указанные * \< * * \<в>языка, *>стран и * \<code_page>* строках. Можно использовать различные сочетания языка, страны или региона и кодовой страницы. Например, этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей 1252.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию ANSI.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию OEM.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Устанавливает язык, указанный * \<языком>, *и использует страну/регион по умолчанию для указанного языка и страницу кода ANSI пользователя по умолчанию для этой страны/региона, полученную из операционной системы хоста. Например, следующие вызовы **для установки** функционально эквивалентны:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Рекомендуется использовать первую форму для обеспечения производительности и простоты обслуживания.

- `setlocale( LC_ALL, ".<code_page>" );`

   Задает кодовую страницу согласно значению, отображаемому *<code_page>*, вместе с языком и страной или регионом по умолчанию (согласно определению операционной системы) для заданной кодовой страницы.

Категория должна быть **LC_ALL** или **LC_CTYPE** для изменения страницы кода. Например, если страна/регион по умолчанию и язык операционной системы хоста являются "Соединенные Штаты" и "Английский", следующие два вызова для **установки** являются функционально эквивалентными:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Дополнительные сведения см. в разделе о pragma-директиве [setlocale](../../preprocessor/setlocale.md) в [Справочнике по препроцессору C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).

Функция [_configthreadlocale](configthreadlocale.md) используется для контроля того, влияет ли **setlocale** на локал из всех потоков в программе или только на локал потока вызывая.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
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
           setlocale(LC_ALL, locale));

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
           setlocale(LC_ALL, "en-US"));

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

[Названия языков, языков и страновых/регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[Языкового стандарта](../../c-runtime-library/locale.md)\
[локонв](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[strcoll Функции](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
