---
title: setlocale, _wsetlocale | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsetlocale
- setlocale
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
- _wsetlocale
- _tsetlocale
- setlocale
dev_langs:
- C++
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 666cb9954569d4c5bd232f387d63e320af52818a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451840"
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale

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

*category*<br/>
Категория, на которую влияет языковой стандарт.

*locale*<br/>
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если допустимый *языкового стандарта* и *категории* заданы, возвращает указатель на строку, связанную с указанным *языкового стандарта* и *категории*. Если *языкового стандарта* или *категории* является недопустимым, возвращается указатель null и текущие параметры языкового стандарта программы не изменяются.

Например, вызов

```C
setlocale( LC_ALL, "en-US" );
```

задает все категории, возвращая только строку

```Output
en-US
```

Можно скопировать строку, возвращаемую **setlocale** для восстановления этой части информации о языковом стандарте программы. Глобальная или локальное хранилище потока используется для строки, возвращаемой **setlocale**. Последующие вызовы **setlocale** перезаписывают эту строку, что аннулирует указатели строк, возвращенные предыдущими вызовами.

## <a name="remarks"></a>Примечания

Используйте **setlocale** функции, чтобы задать, изменить или запроса некоторой или всей текущего языкового стандарта программы, определяемое *языкового стандарта* и *категории*. *языковой стандарт* относится к расположению (Страна или регион и язык), для которого можно настраивать определенные аспекты программы. К некоторым категориям, зависящим от языкового стандарта, относится формат дат и отображения денежных значений. Если задать *языкового стандарта* строка по умолчанию для языка, который имеет несколько форм, которые поддерживаются на вашем компьютере, следует проверить **setlocale** возвращают значение, чтобы узнать, какой язык применяется. Например, если задать *языкового стандарта* значение «китайский» возвращаемое значение может быть либо «китайский (упрощенный)», либо «китайский (традиционный)».

**_wsetlocale** — это двухбайтовая версия **setlocale**; *языкового стандарта* аргумент и возвращаемое значение **_wsetlocale** представляют собой строки расширенных символов. **_wsetlocale** и **setlocale** ведут себя идентично.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

*Категории* аргумент указывает части информации о языковом стандарте программы, которые затрагиваются. Макросы, используемые для *категории* и части программы, они влияют на следующие:

|*Категория* флаг|Затрагивает|
|-|-|
**LC_ALL**|Все категории, перечисленные ниже.
**LC_COLLATE**|**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_ strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, и **wcsxfrm** функции.
**LC_CTYPE**|Функции обработки символов (за исключением **isdigit**, **isxdigit**, **mbstowcs**, и **mbtowc**, которые не затрагиваются).
**LC_MONETARY**|Форматирование денежных информацию, возвращаемую **localeconv** функции.
**LC_NUMERIC**|Символ для процедур форматированного вывода десятичной запятой (например, **printf**), для процедур преобразования данных и не относящихся к денежным форматирования сведения, возвращенные **localeconv**. Помимо символа десятичного разделителя **LC_NUMERIC** задает разделитель тысяч и группирование управления строку, возвращаемую [localeconv](localeconv.md).
**LC_TIME**|**Strftime** и **wcsftime** функции.

Эта функция проверяет параметр категории. Если параметр категории не является одним из значений, приведенных в предыдущей таблице, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция устанавливает **errno** для **EINVAL** и возвращает **NULL**.

*Языкового стандарта* аргумент — указатель на строку, которая задает языковой стандарт. Сведения о формате параметра *языкового стандарта* аргумент, в разделе [имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Если аргумент *locale* указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией. Значение **C** задает минимальную подходящую ANSI среду для переноса c. **C** языкового стандарта предполагается, что все **char** типы данных — 1 байт, и их значение всегда меньше 256.

При запуске программы выполняется эквивалент следующего оператора:

`setlocale( LC_ALL, "C" );`

*Языкового стандарта* аргумент может принимать имя языкового стандарта, строки с названием языка, строки с названием языка и код страны или региона, кодовую страницу или строку языка, код страны или региона и кодовой страницы. Набор доступных имен языкового стандарта, названий языков, кодов страны и кодовых страниц включает все поддерживаемые API многоязыковой поддержки Windows, кроме кодовых страниц, требующих более 2 байт на один знак, таких как UTF-7 и UTF-8. Если указать значение кодовой страницы UTF-7 или UTF-8, **setlocale** завершится ошибкой, возвращая **NULL**. Набор имен языковых стандартов, поддерживаемых **setlocale** описаны в [имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строк языка и страны или региона, поддерживаемых **setlocale** , перечислены в [строки языка](../../c-runtime-library/language-strings.md) и [стран и регионов](../../c-runtime-library/country-region-strings.md). Рекомендуется использовать форму имени языкового стандарта для обеспечения производительности и удобства поддержки строк языкового стандарта, внедренных в код или сериализованных в хранилище. Строковые значения имен языкового стандарта реже подвергаются изменению обновлением операционной системы, чем язык и форма названия страны или региона.

Указатель null, которое передается как *языкового стандарта* аргумент сообщает **setlocale** выполнить запрос, а не задать международную среду. Если *языкового стандарта* аргумент является указателем null, Настройка текущего языкового стандарта программы не меняется. Вместо этого **setlocale** возвращает указатель на строку, связанный с *категории* языкового стандарта текущего потока. Если *категории* аргумент **LC_ALL**, функция возвращает строку, которая указывает текущий параметр каждой категории, разделенных точкой с запятой. Например, последовательность вызовов

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

returns

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

Это строка, с которым связан **LC_ALL** категории.

Следующие примеры относятся к **LC_ALL** категории. Каждую из строк ".OCP" и ".ACP" можно использовать вместо номера кодовой страницы для определения использования заданной по умолчанию для пользователя кодовой страницы OEM и заданной по умолчанию для пользователя кодовой страницы ANSI, соответственно.

- `setlocale( LC_ALL, "" );`

   Задает языковой стандарт по умолчанию, т.е. заданную по умолчанию для пользователя кодовую страницу ANSI, полученную от операционной системы.

- `setlocale( LC_ALL, ".OCP" );`

   Явно задает языковой стандарт согласно текущей кодовой странице OEM, полученной от операционной системы.

- `setlocale( LC_ALL, ".ACP" );`

   Задает языковой стандарт согласно текущей кодовой странице ANSI, полученной от операционной системы.

- `setlocale( LC_ALL, "<localename>" );`

   Задает языковой стандарт согласно имени языкового стандарта, отображаемому *\<localename>*.

- `setlocale( LC_ALL, "<language>_<country>" );`

   Задает языковой стандарт согласно языку и стране или региону, отображаемым *\<language>* и *\<country>*, вместе с кодовой страницей по умолчанию, полученной от операционной системы.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Задает языковой стандарт для языка, страны или региона и кодовой страницы обозначается  *\<языка >*,  *\<страны >*, и  *\<code_page >* строки. Можно использовать различные сочетания языка, страны или региона и кодовой страницы. Например, этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей 1252.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию ANSI.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию OEM.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Задает языковой стандарт согласно языку, отображаемому *\<language>*, и использует страну или регион по умолчанию для определенного языка и заданную по умолчанию для пользователя кодовую страницу ANSI для этой страны или региона согласно данным, полученным от операционной системы. Например, следующие вызовы **setlocale** функционально эквивалентны:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Рекомендуется использовать первую форму для обеспечения производительности и простоты обслуживания.

- `setlocale( LC_ALL, ".<code_page>" );`

   Задает кодовую страницу согласно значению, отображаемому *<code_page>*, вместе с языком и страной или регионом по умолчанию (согласно определению операционной системы) для заданной кодовой страницы.

Эта категория должна быть **LC_ALL** или **LC_CTYPE** для реализации изменения кодовой страницы. Например, если по умолчанию Страна или регион и язык операционной системы являются «Соединенные Штаты» и «Английский», следующие два вызова **setlocale** функционально эквивалентны:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Дополнительные сведения см. в разделе о pragma-директиве [setlocale](../../preprocessor/setlocale.md) в [Справочнике по препроцессору C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).

Функция [_configthreadlocale](configthreadlocale.md) можно указать, является ли **setlocale** влияет языковой стандарт всех потоков в программе или только на языковой стандарт вызывающего потока.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

    // Configure per-thread locale to cause all subsequently created
    // threads to have their own locale.
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

## <a name="see-also"></a>См. также

[Имени языкового стандарта, языков и стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
