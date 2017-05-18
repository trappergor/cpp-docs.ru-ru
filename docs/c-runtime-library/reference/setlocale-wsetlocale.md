---
title: "setlocale, _wsetlocale | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5a83ef5640a72dcd2ff8f7f35c587789dff35d61
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale
Устанавливает или извлекает языковой стандарт времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *setlocale(  
   int category,  
   const char *locale   
);  
wchar_t *_wsetlocale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `category`  
 Категория, на которую влияет языковой стандарт.  
  
 `locale`  
 Указатель языкового стандарта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если даны действительные `locale` и `category`, возвращает указатель на строку, связанную с указанным `locale` и `category`. Если `locale` или `category` недействительны, возвращает указатель null, и текущие параметры языкового стандарта программы не изменяются.  
  
 Например, вызов  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 задает все категории, возвращая только строку  
  
 `en-US`  
  
 Можно скопировать строку, возвращенную `setlocale`, для восстановления этой части данных о языковом стандарте программы. Глобальное или локальное хранилище потока используется для строки, возвращаемой `setlocale`. Последующие вызовы `setlocale` перезаписывают эту строку, что аннулирует указатели строк, возвращенные предыдущими вызовами.  
  
## <a name="remarks"></a>Примечания  
 Используйте функцию `setlocale` для задания, изменения или получения некоторой или всей информации о языковом стандарте текущей программы, определяемой `locale` и `category`. `locale` ссылается на расположение (страну или регион и язык), для которого можно настраивать определенные аспекты программы. К некоторым категориям, зависящим от языкового стандарта, относится формат дат и отображения денежных значений. Если для `locale` задается строка по умолчанию для языка с несколькими формами, которые поддерживаются на вашем компьютере, необходимо проверять возвращаемое значение `setlocale`, чтобы узнать, какой язык применяется. Например, если для `locale` задано значение «китайский», возвращаемое значение может быть либо «китайский (упрощенный)», либо «китайский (традиционный)».  
  
 `_wsetlocale` — это версия с расширенными символами для `setlocale`; аргумент `locale` и возвращаемое значение `_wsetlocale` являются строками с расширенными символами. Поведение `_wsetlocale` и `setlocale` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|  
  
 Аргумент `category` указывает части информации о языковом стандарте программы, которые подвергаются влиянию. Макросы, используемые для `category` и части программы, на которые они оказывают, указаны ниже.  
  
 `LC_ALL`  
 Все категории в следующем списке.  
  
 `LC_COLLATE`  
 Функции `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` и `wcsxfrm`.  
  
 `LC_CTYPE`  
 Функции обработки символов (за исключением `isdigit`, `isxdigit`, `mbstowcs` и `mbtowc`, которые не затрагиваются).  
  
 `LC_MONETARY`  
 Информация о форматировании денежных значений, возвращаемая функцией `localeconv`.  
  
 `LC_NUMERIC`  
 Символ десятичного разделителя для информации процедур форматированного вывода (например, `printf`), для процедур преобразования данных и для форматирования не относящихся к денежным значений, возвращаемой `localeconv`. Помимо символа десятичного разделителя `LC_NUMERIC` также задает разделитель тысяч и строку элемента управления группировкой, возвращаемую [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Функции `strftime` и `wcsftime`.  
  
 Эта функция проверяет параметр категории. Если параметр категории не является одним из значений, приведенных в предыдущей таблице, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `NULL`.  
  
 Аргумент `locale` является указателем на строку, которая задает языковой стандарт. Дополнительные сведения о формате аргумента `locale` см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Если `locale` указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией. Значение `C` задает минимальную подходящую ANSI среду для переноса C. Языковой стандарт `C` предполагает, что все типы данных `char` соответствуют 1 байту, а их значение всегда меньше 256.  
  
 При запуске программы выполняется эквивалент следующего оператора:  
  
 `setlocale( LC_ALL, "C" );`  
  
 Аргумент `locale` может принимать имя языкового стандарта, строковую переменную с названием языка, строковую переменную с названием языка и код страны или региона, кодовую страницу или строковую переменную с названием языка, код страны или региона и кодовую страницу. Набор доступных имен языкового стандарта, названий языков, кодов страны и кодовых страниц включает все поддерживаемые API многоязыковой поддержки Windows, кроме кодовых страниц, требующих более 2 байт на один знак, таких как UTF-7 и UTF-8. Если указать значение кодовой страницы UTF-7 или UTF-8, `setlocale` завершится ошибкой, возвращая значение NULL. Набор имен языковых стандартов, поддерживаемых `setlocale`, см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строковых значений языка и страны или региона, поддерживаемых `setlocale`, представлен в разделах [Строки языка](../../c-runtime-library/language-strings.md) и [Строки страны или региона](../../c-runtime-library/country-region-strings.md). Рекомендуется использовать форму имени языкового стандарта для обеспечения производительности и удобства поддержки строк языкового стандарта, внедренных в код или сериализованных в хранилище. Строковые значения имен языкового стандарта реже подвергаются изменению обновлением операционной системы, чем язык и форма названия страны или региона.  
  
 Указатель null, который передается в качестве аргумента `locale`, указывает `setlocale` выполнить запрос, а не задать международную среду. Если аргумент `locale` является указателем null, настройка текущего языкового стандарта программы не меняется. Вместо этого `setlocale` возвращает указатель на строку, связанную с `category` текущего языкового стандарта этого потока. Если аргумент `category` имеет значение `LC_ALL`, функция возвращает строку, которая указывает текущий параметр каждой категории с разделением точкой с запятой. Например, последовательность вызовов  
  
 `// Set all categories and return "en-US"`  
  
 `setlocale(LC_ALL, "en-US");`  
  
 `// Set only the LC_MONETARY category and return "fr-FR"`  
  
 `setlocale(LC_MONETARY, "fr-FR");`  
  
 `printf("%s\n", setlocale(LC_ALL, NULL));`  
  
 returns  
  
 `LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US`  
  
 и это строка, связанная с категорией `LC_ALL`.  
  
 Следующие примеры относятся к категории `LC_ALL`. Каждую из строк ".OCP" и ".ACP" можно использовать вместо номера кодовой страницы для определения использования заданной по умолчанию для пользователя кодовой страницы OEM и заданной по умолчанию для пользователя кодовой страницы ANSI, соответственно.  
  
 `setlocale( LC_ALL, "" );`  
 Задает языковой стандарт по умолчанию, т.е. заданную по умолчанию для пользователя кодовую страницу ANSI, полученную от операционной системы.  
  
 `setlocale( LC_ALL, ".OCP" );`  
 Явно задает языковой стандарт согласно текущей кодовой странице OEM, полученной от операционной системы.  
  
 `setlocale( LC_ALL, ".ACP" );`  
 Задает языковой стандарт согласно текущей кодовой странице ANSI, полученной от операционной системы.  
  
 `setlocale( LC_ALL, "<localename>" );`  
 Задает языковой стандарт согласно имени языкового стандарта, отображаемому *\<localename>*.  
  
 `setlocale( LC_ALL, "<language>_<country>" );`  
 Задает языковой стандарт согласно языку и стране или региону, отображаемым *\<language>* и *\<country>*, вместе с кодовой страницей по умолчанию, полученной от операционной системы.  
  
 `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`  
 Задает языковой стандарт согласно языку, стране или региону и кодовой странице, отображаемым строками *\<language>*, *\<country>* и *<code_page>*. Можно использовать различные сочетания языка, страны или региона и кодовой страницы. Например, этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей 1252.  
  
 `setlocale( LC_ALL, "French_Canada.1252" );`  
  
 Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию ANSI.  
  
 `setlocale( LC_ALL, "French_Canada.ACP" );`  
  
 Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию OEM.  
  
 `setlocale( LC_ALL, "French_Canada.OCP" );`  
  
 `setlocale( LC_ALL, "<language>" );`  
 Задает языковой стандарт согласно языку, отображаемому *\<language>*, и использует страну или регион по умолчанию для определенного языка и заданную по умолчанию для пользователя кодовую страницу ANSI для этой страны или региона согласно данным, полученным от операционной системы. Например, следующие вызовы `setlocale` функционально эквивалентны:  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 `setlocale( LC_ALL, "English" );`  
  
 `setlocale( LC_ALL, "English_United States.1252" );`  
  
 Рекомендуется использовать первую форму для обеспечения производительности и простоты обслуживания.  
  
 `setlocale( LC_ALL, ".<code_page>" );`  
 Задает кодовую страницу согласно значению, отображаемому *<code_page>*, вместе с языком и страной или регионом по умолчанию (согласно определению операционной системы) для заданной кодовой страницы.  
  
 Эта категория должна быть `LC_ALL` или `LC_CTYPE` для реализации изменения кодовой страницы. Например, если страной и языком по умолчанию операционной системы являются «Соединенные Штаты» и «английский», следующие два вызова `setlocale` функционально эквивалентны:  
  
 `setlocale( LC_ALL, ".1252" );`  
  
 `setlocale( LC_ALL, "English_United States.1252");`  
  
 Дополнительные сведения см. в разделе о pragma-директиве [setlocale](../../preprocessor/setlocale.md) в [Справочнике по препроцессору C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).  
  
 Функция [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) используется в для определения того, влияет ли `setlocale` на языковой стандарт всех потоков в программе или только на языковой стандарт вызывающего потока.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`setlocale`|\<locale.h>|  
|`_wsetlocale`|\<locale.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
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
 [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
