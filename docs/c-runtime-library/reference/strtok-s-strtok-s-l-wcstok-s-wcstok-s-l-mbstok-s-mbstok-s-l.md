---
title: "strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcstok_s_l"
  - "_mbstok_s_l"
  - "_mbstok_s"
  - "strtok_s"
  - "wcstok_s"
  - "_strtok_s_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstok_s_l"
  - "_wcstok_s_l"
  - "_tcstok_s"
  - "_mbstok_s_l"
  - "strtok_s"
  - "wcstok_s"
  - "_mbstok_s"
  - "_strtok_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstok_s - функция"
  - "_mbstok_s_l - функция"
  - "_strtok_s_l - функция"
  - "_tcstok_s - функция"
  - "_tcstok_s_l - функция"
  - "_wcstok_s_l - функция"
  - "mbstok_s - функция"
  - "mbstok_s_l - функция"
  - "строки [C++], поиск"
  - "strtok_s - функция"
  - "strtok_s_l - функция"
  - "лексемы, поиск в строках"
  - "wcstok_s - функция"
  - "wcstok_s_l - функция"
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Находит следующий токен в строке, с помощью текущего или переданного языкового стандарта.  В этих версиях [strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../Topic/strtok,%20_strtok_l,%20wcstok,%20_wcstok_l,%20_mbstok,%20_mbstok_l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  `_mbstok_s` и `_mbstok_s_l` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
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
  
#### Параметры  
 `strToken`  
 Строка, содержащая токен или токены.  
  
 `strDelimit`  
 Набор разделителей.  
  
 `context`  
 Используется для хранения данных о положении между вызовами метода `strtok_s`  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращает указатель на следующий токен, найденный в `strToken`.  Они возвращают `NULL`, если ни одного токена больше не удается найти.  Каждый вызов изменяет `strToken`, заменяя символом `NULL` на первый разделитель, находящийся после возвращенного токена.  
  
### Условия возникновения ошибки  
  
|`strToken`|`strDelimit`|`context`|Возвращаемое значение|`errno`|  
|----------------|------------------|---------------|---------------------------|-------------|  
|`NULL`|any|указатель на пустой указатель.|`NULL`|`EINVAL`|  
|any|`NULL`|any|`NULL`|`EINVAL`|  
|any|any|`NULL`|`NULL`|`EINVAL`|  
  
 Если `strToken` равен `NULL`, но контекст \- допустимый указатель на контекст, ошибки нет.  
  
## Заметки  
 Функция `strtok_s` находит следующий токен в `strToken`.  Набор символов в `strDelimit` указывает возможные разделители токенов, которые необходимо найти в `strToken` во время текущего вызова.  `wcstok_s` и `_mbstok_s`являются версиями функции `strtok_s` для расширенных и многобайтовых символов.  Аргументы и возвращаемые значения `wcstok_s` и `_wcstok_s_l` представляют собой строки расширенных символов; аргументы и возвращаемые значения `_mbstok_s` и `_mbstok_s_l` представляют собой строки многобайтовых символов.  В остальных случаях эти три функции ведут себя идентично.  
  
 Эта функция проверяет свои параметры.  Если возникает условие ошибки, которое показано в таблице условий ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `NULL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 При первом вызове `strtok_s` функция пропускает ведущие разделители и возвращает указатель на первый токен в `strToken`, ставя в конец токена нуль\-символ.  Из оставшейся части `strToken` можно выделить больше токенов с помощью серии вызовов `strtok_s`.  Каждый вызов `strtok_s` изменяет `strToken`, вставляя нуль\-символ после токена, возвращаемого этим вызовом.  Указатель `context` продолжает отслеживать то, какая строка читается и откуда в строку читать следующий токен.  Чтобы прочитать следующий токен из `strToken`, вызовите `strtok_s` со значением `NULL` для аргумента `strToken` и передайте тот же параметр `context`.  Аргумент `strToken` со значением `NULL` приводит к тому, что `strtok_s` ищет следующий токен в измененной  `strToken`.  Аргумент `strDelimit` может принимать любое значение из одного вызова к другому, чтобы набор разделителей мог меняться.  
  
 Поскольку параметр `context` заменяет статические буферы, используемые в `strtok` и `_strtok_l`, можно проанализировать две строки одновременно в одном потоке.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtok_s`|\<string.h\>|  
|`_strtok_s_l`|\<string.h\>|  
|`wcstok_s,`<br /><br /> `_wcstok_s_l`|\<string.h\> или \<wchar.h\>|  
|`_mbstok_s,`<br /><br /> `_mbstok_s_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
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
  
  **Tokens:**  
 **A**  
 **Другое действие .**  
 **string**  
 **string**  
 **of**  
 **parsed**  
 **tokens**  
 **at**  
 **и**  
 **в разделе ,**  
 **some**  
 **same**  
 **more**  
 **времени.**  
 **tokens**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)