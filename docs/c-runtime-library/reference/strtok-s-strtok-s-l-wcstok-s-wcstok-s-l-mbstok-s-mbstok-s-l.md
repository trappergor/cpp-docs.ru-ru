---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
ms.date: 4/2/2020
api_name:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
- _o__mbstok_s
- _o__mbstok_s_l
- _o_strtok_s
- _o_wcstok_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
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
ms.openlocfilehash: 9fe89fb897a5459b16c49060359b4bb40bc062a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365223"
---
# <a name="strtok_s-_strtok_s_l-wcstok_s-_wcstok_s_l-_mbstok_s-_mbstok_s_l"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Находит следующий токен в строке с использованием текущего или переданного языкового стандарта. Эти версии [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) отличаются повышенной безопасностью (см. раздел [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md)).

> [!IMPORTANT]
> **_mbstok_s** и **_mbstok_s_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
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

unsigned char* _mbstok_s_l(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Строка, содержащая маркер или маркеры для поиска.

*Разделители*<br/>
Набор символов делимитемых для использования.

*context*<br/>
Используется для хранения информации о положении между вызовами в функцию.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий маркер, найденный в *str*. Возвращает **NULL,** когда больше не найдено токенов. Каждый вызов изменяет *str,* заменяя нулевой символ для первого делимитера, который происходит после возвращенного маркера.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Ул*|*Разделители*|*context*|Возвращаемое значение|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**Null**|any|указатель на указатель NULL|**Null**|**EINVAL**|
|any|**Null**|any|**Null**|**EINVAL**|
|any|any|**Null**|**Null**|**EINVAL**|

Если *str* str **null,** но *контекст* является указателем на допустимый указатель контекста, ошибки нет.

## <a name="remarks"></a>Remarks

**Семейство strtok_s** функций находит следующий маркер в *str*. Набор символов в *делимитерах* определяет возможные делимитеры маркера, которые можно найти в *str* на текущем вызове. **wcstok_s** и **_mbstok_s** являются широкохарактерными и многобайтными версиями **strtok_s.** Аргументы и значения возврата **wcstok_s** и **_wcstok_s_l** являются широкохарактерными строками; _mbstok_s **и** **_mbstok_s_l** являются многобайтными строками. В остальном эти функции ведут себя одинаково.

Эта функция проверяет свои параметры. При возникновении условия ошибки, как в таблице Условий ошибки, вызывается недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **NULL**.

При первом вызове **strtok_s**функция пропускает ведущие делимитемыи и возвращает указатель на первый маркер в *str,* прекращая токен с нулевым символом. Больше токенов может быть разбито из оставшейся *части str* серией звонков в **strtok_s.** Каждый вызов **для strtok_s** изменяет *str* путем вставки нулевой символ после того, как маркер вернулся этим вызовом. Указатель *контекста* отслеживает, какая строка читается и где в строке будет прочитан следующий маркер. Чтобы прочитать следующий маркер из *str,* позвоните **strtok_s** с значением **NULL** для аргумента *str* и пройдите тот же параметр *контекста.* Аргумент **NULL** *str* заставляет **strtok_s** искать следующий маркер в модифицированном *str*. Аргумент *делимитеров* может принимать любое значение от одного вызова к другому, так что набор делимитеров может меняться.

Поскольку параметр *контекста* вытесняет статические буферы, используемые в **strtok** и **_strtok_l,** можно разосмотреть две строки одновременно в одном потоке.

Значение вывода зависит от настройки **LC_CTYPE** категории локализуем локализовать. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md).

Версии этих функций без **_l** суффикса используют текущий локаль потока для этого поведения, зависящем от локализации. Версии с **_l** суффикса идентичны, за исключением того, что они вместо этого используют место, указанное параметром *локализации.* Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**,<br />**_wcstok_s_l**|\<string.h> или \<wchar.h>|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|\_UNICODE \_& MBCS не определены|\_Определено MBCS|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok_s**|**strtok_s**|**_mbstok_s**|**wcstok_s**|
|**_tcstok_s_l**|**_strtok_s_l**|**_mbstok_s_l**|**_wcstok_s_l**|

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

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
