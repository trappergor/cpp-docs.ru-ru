---
title: "Функции strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
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
dev_langs: C++
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
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5d5b92497bedcfd766975e62c886dd64676fc71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Находит следующий токен в строке с использованием текущего или переданного языкового стандарта. Эти версии [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) отличаются повышенной безопасностью (см. раздел [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md)).  
  
> [!IMPORTANT]
>  Функции `_mbstok_s` и `_mbstok_s_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```
char* strtok_s(  
   char* str,  
   const char* delimiters,  
   char** context  
);

char* _strtok_s_l(  
   char* str,  
   const char* delimiters,  
   char** context,  
   _locale_t locale  
);  

wchar_t* wcstok_s(  
   wchar_t* str,  
   const wchar_t* delimiters,   
   wchar_t** context  
); 
 
wchar_t *_wcstok_s_l(  
   wchar_t* str,  
   const wchar_t* delimiters,   
   wchar_t** context,  
   _locale_t locale  
);  

unsigned char* _mbstok_s(  
   unsigned char* str,  
   const unsigned char* delimiters,   
   char** context  
);  

unsigned char* _mbstok_s(  
   unsigned char* str,  
   const unsigned char* delimiters,   
   char** context,  
   _locale_t locale  
);  
```  
  
### <a name="parameters"></a>Параметры  

*str*  
Строка, содержащая токен или токены для поиска.  
  
*разделители*  
Набор символов-разделителей для использования.  
  
*контекст*  
Используется для хранения данных о положении между вызовами функции.  
  
*locale*  
Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  

Возвращает указатель на следующий токен, найденный в *str*. Возвращает `NULL` при нет больше токенов не найдено. Каждый вызов изменяет строку *str* путем замены `NULL` символ первый разделитель, находящийся после возвращенного токена.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|*str*|*разделители*|*контекст*|Возвращаемое значение|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|any|указатель на указатель NULL|`NULL`|`EINVAL`|  
|any|`NULL`|any|`NULL`|`EINVAL`|  
|any|any|`NULL`|`NULL`|`EINVAL`|  
  
Если *str* — `NULL` , но *контекста* является указатель на указатель допустимый контекст не содержит ошибок.  
  
## <a name="remarks"></a>Примечания  

`strtok_s` Семейство функций находит следующий токен в *str*. Набор символов в *разделители* указывает возможные разделители токенов, должно быть найдено в *str* во время текущего вызова. Функции `wcstok_s` и `_mbstok_s` являются версиями функции `strtok_s` для расширенных и многобайтовых символов. Аргументы и возвращаемые значения функций `wcstok_s` и `_wcstok_s_l` представляют собой строки расширенных символов; аргументы и возвращаемые значения функций `_mbstok_s` и `_mbstok_s_l` представляют собой строки многобайтовых символов. В остальном эти функции ведут себя одинаково.  

Эта функция проверяет свои параметры. При возникновении условия ошибки, описанного в таблице условий ошибок, вызывается обработчик недопустимого параметра. Это описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `NULL`.

При первом вызове для `strtok_s` функция пропускает ведущие разделители и возвращает указатель на первый токен в *str*, завершая токен нуль-символом. Можно выделить другие токены из оставшейся части *str* с помощью последовательных вызовов `strtok_s`. Каждый вызов `strtok_s` изменяет *str* , вставляя нуль-символ после токена, возвращенного этим вызовом. *Контекста* отслеживает отслеживания объекта указатель, какая строка считывается и где в строке следующий токен — для чтения. Чтобы прочитать следующий токен из *str*, вызовите `strtok_s` с `NULL` значение для *str* аргумента и передайте тот же *контекста* параметра. `NULL` *Str* аргумент причины `strtok_s` для поиска следующий токен в измененной *str*. *Разделители* аргумент может принимать любое значение от одного вызова к следующему, позволяя изменять набор разделителей.

Поскольку *контекста* параметра заменяет статические буферы, используемые в `strtok` и `_strtok_l`, можно анализировать две строки одновременно в одном потоке.

Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без `_l` суффикс использовать языкового стандарта текущего потока для данного поведения, зависящего от языкового стандарта. Версии с `_l` суффиксом идентичны, за исключением того, что они используют *языкового стандарта* параметра. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`strtok_s`|\<string.h>|
|`_strtok_s_l`|\<string.h>|
|`wcstok_s`,<br />`_wcstok_s_l`|\<string.h> или \<wchar.h>|
|`_mbstok_s`,<br />`_mbstok_s_l`|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|\_Юникод & \_MBCS не определены|\_Определенные многобайтовой Кодировки|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|

## <a name="example"></a>Пример

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

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

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
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