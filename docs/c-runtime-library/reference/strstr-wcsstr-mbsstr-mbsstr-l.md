---
title: strstr, wcsstr, _mbsstr, _mbsstr_l
ms.date: 11/04/2016
api_name:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
ms.openlocfilehash: 8c113e02f308b634b6bcb8aea6e46fc14b9abd92
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946588"
---
# <a name="strstr-wcsstr-_mbsstr-_mbsstr_l"></a>strstr, wcsstr, _mbsstr, _mbsstr_l

Возвращает указатель на первое вхождение искомой строки в строке.

> [!IMPORTANT]
> Функции `_mbsstr` и `_mbsstr_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *strstr(
   const char *str,
   const char *strSearch
); // C only
char *strstr(
   char *str,
   const char *strSearch
); // C++ only
const char *strstr(
   const char *str,
   const char *strSearch
); // C++ only
wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C only
wchar_t *wcsstr(
   wchar_t *str,
   const wchar_t *strSearch
); // C++ only
const wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C++ only
unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C only
unsigned char *_mbsstr(
   unsigned char *str,
   const unsigned char *strSearch
); // C++ only
const unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C++ only
unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C only
unsigned char *_mbsstr_l(
   unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
const unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка для поиска, завершающаяся символом NULL.

*стрсеарч*<br/>
Искомая строка, завершающаяся символом NULL.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на первое вхождение *стрсеарч* в *str*или значение null, если *стрсеарч* не отображается в *str*. Если *стрсеарч* указывает на строку нулевой длины, функция возвращает *str*.

## <a name="remarks"></a>Примечания

Функция возвращает указатель на первое вхождение стрсеарч в *str*. `strstr` Поиск не включает завершающие нуль-символы. `wcsstr` является версией `strstr` с расширенными символами, а `_mbsstr` — версией с многобайтовыми символами. Аргументы и возвращаемое значение `wcsstr` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbsstr` представляют собой многобайтовые строки. `_mbsstr` проверяет свои параметры. Если *str* или *стрсеарч* имеет значение null, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено `_mbsstr` , `errno` присваивает свойству значение еинвал и возвращает значение 0. Функции `strstr` и `wcsstr` не проверяют свои параметры. В остальном эти три функции ведут себя идентично.

> [!IMPORTANT]
> Эти функции могут создать угрозу в связи с проблемой переполнения буфера. Проблемы переполнения буфера могут использоваться для атаки на систему, поскольку они могут допустить выполнение произвольного кода, приводящего к несанкционированному повышению прав доступа. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

В C эти функции принимают указатель **const** для первого аргумента. В языке C++ доступны две перегрузки. Перегрузка, которая принимает указатель на **const** , возвращает указатель на **константу**; версия, принимающая указатель на non-**const** , возвращает указатель на**неконстантный**. Макрос _CRT_CONST_CORRECT_OVERLOADS определяется, если доступны и **константные** , и**неконстантные** версии этих функций. Если требуется поведение, не являющееся**константой** , для C++ обеих перегрузок, определите символ _CONST_RETURN.

На выходное значение влияет настройка LC_CTYPE в категории locale; Дополнительные сведения см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md). Версии этих функций, не имеющие суффикса **_l** , используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. версии с суффиксом **_l** идентичны за исключением того, что вместо них используется переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**Н/Д**|**Н/Д**|`_mbsstr_l`|**Н/Д**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> или \<wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strstr.c

#include <string.h>
#include <stdio.h>

char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int  result;
   printf( "String to be searched:\n   %s\n", string );
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );
   pdest = strstr( string, str );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "%s found at position %d\n", str, result );
   else
      printf( "%s not found\n", str );
}
```

```Output
String to be searched:
   The quick brown dog jumps over the lazy fox
            1         2         3         4         5
   12345678901234567890123456789012345678901234567890

lazy found at position 36
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::find](../../standard-library/basic-string-class.md#find)<br/>
