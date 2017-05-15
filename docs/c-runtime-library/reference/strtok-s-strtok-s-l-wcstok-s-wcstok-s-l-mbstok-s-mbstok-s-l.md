---
title: "Функции strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
dev_langs:
- C++
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4313f785ba5197c3659e74384b7d6ecda8e8c7be
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
Находит следующий токен в строке с использованием текущего или переданного языкового стандарта. Эти версии [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) отличаются повышенной безопасностью (см. раздел [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md)).  
  
> [!IMPORTANT]
> Функции  `_mbstok_s` и `_mbstok_s_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      char *strtok_s(  
char *strToken,  
const char *strDelimit,  
   char **context  
);  
char *_strtok_s_l(  
char *strToken,  
const char *strDelimit,  
   char **context,  
_locale_tlocale  
);  
wchar_t *wcstok_s(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context  
);  
wchar_t *_wcstok_s_l(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context,  
_locale_tlocale  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context,  
_locale_tlocale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `strToken`  
 Строка, содержащая токен или токены.  
  
 `strDelimit`  
 Набор символов-разделителей.  
  
 `context`  
 Используется для хранения данных о положении между вызовами функции `strtok_s`  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на следующий токен, найденный в `strToken`. Они возвращают `NULL`, если больше токенов не найдено. Каждый вызов изменяет строку `strToken`, заменяя символом `NULL` первый разделитель, находящийся после возвращенного токена.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`strToken`|`strDelimit`|`context`|Возвращаемое значение|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|любые|указатель на указатель NULL|`NULL`|`EINVAL`|  
|любые|`NULL`|любые|`NULL`|`EINVAL`|  
|любые|любые|`NULL`|`NULL`|`EINVAL`|  
  
 Если `strToken` имеет значение `NULL`, но контекст — допустимый указатель на контекст, ошибки нет.  
  
## <a name="remarks"></a>Примечания  
 Функция `strtok_s` находит следующий токен в `strToken`. Набор символов в параметре `strDelimit` указывает возможные разделители токенов, которые требуется найти в `strToken` во время текущего вызова. Функции `wcstok_s` и `_mbstok_s` являются версиями функции `strtok_s` для расширенных и многобайтовых символов. Аргументы и возвращаемые значения функций `wcstok_s` и `_wcstok_s_l` представляют собой строки расширенных символов; аргументы и возвращаемые значения функций `_mbstok_s` и `_mbstok_s_l` представляют собой строки многобайтовых символов. В остальном эти три функции ведут себя идентично.  
  
 Эта функция проверяет свои параметры. При возникновении условия ошибки, описанного в таблице условий ошибок, вызывается обработчик недопустимого параметра. Это описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `NULL`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 При первом вызове функции `strtok_s` она пропускает ведущие разделители и возвращает указатель на первый токен в `strToken`, завершая токен нуль-символом. Из оставшейся части `strToken` можно выделить другие токены с помощью последовательных вызовов функции `strtok_s`. Каждый вызов функции `strtok_s` изменяет `strToken`, вставляя нуль-символ после токена, возвращенного этим вызовом. Указатель `context` продолжает отслеживать читаемую строку и место в строке, из которого следует считать следующий токен. Чтобы прочитать следующий токен из `strToken`, вызовите функцию `strtok_s` со значением `NULL` для аргумента `strToken` и передайте тот же параметр `context`. Значение `NULL` аргумента `strToken` приводит к тому, что функция `strtok_s` ищет следующий токен в измененной строке `strToken`. Аргумент `strDelimit` в разных вызовах может принимать любое значение, позволяя изменять набор разделителей.  
  
 Поскольку параметр `context` заменяет статические буферы, используемые в функциях `strtok` и `_strtok_l`, в одном потоке можно анализировать две строки одновременно.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данного поведения, зависимого от языкового стандарта. Версии с суффиксом `_l` идентичны, однако они используют переданный параметр языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strtok_s`|\<string.h>|  
|`_strtok_s_l`|\<string.h>|  
|`wcstok_s`,<br /><br /> `_wcstok_s_l`|\<string.h> или \<wchar.h>|  
|`_mbstok_s`,<br /><br /> `_mbstok_s_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_strtok_s.c  
// In this program, a loop uses strtok_s  
// to print all the tokens (separated by commas  
// or blanks) in two strings at the same time.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
char string1[] =  
    "A string\tof ,,tokens\nand some  more tokens";  
char string2[] =  
    "Another string\n\tparsed at the same time.";  
char seps[]   = " ,\t\n";  
char *token1 = NULL;  
char *token2 = NULL;  
char *next_token1 = NULL;  
char *next_token2 = NULL;  
  
int main( void )  
{  
    printf( "Tokens:\n" );  
  
    // Establish string and get the first token:  
    token1 = strtok_s( string1, seps, &next_token1);  
    token2 = strtok_s ( string2, seps, &next_token2);  
  
    // While there are tokens in "string1" or "string2"  
    while ((token1 != NULL) || (token2 != NULL))  
    {  
        // Get next token:  
        if (token1 != NULL)  
        {  
            printf( " %s\n", token1 );  
            token1 = strtok_s( NULL, seps, &next_token1);  
        }  
        if (token2 != NULL)  
        {  
            printf("        %s\n", token2 );  
            token2 = strtok_s (NULL, seps, &next_token2);  
        }  
    }  
}  
```  
  
```Output  
Tokens:  
 A  
        Another  
 string  
        string  
 of  
        parsed  
 tokens  
        at  
 and  
        the  
 some  
        same  
 more  
        time.  
 tokens  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
