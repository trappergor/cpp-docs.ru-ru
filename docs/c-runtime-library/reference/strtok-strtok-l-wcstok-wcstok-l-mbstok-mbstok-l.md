---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
ms.date: 4/2/2020
api_name:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
- _o__mbstok
- _o__mbstok_l
- _o_strtok
- _o_wcstok
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
ms.openlocfilehash: 7d8f0d889d58fe776e53f78955fff7fd1cdfa40f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912636"
---
# <a name="strtok-_strtok_l-wcstok-_wcstok_l-_mbstok-_mbstok_l"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Находят следующий токен в строке с использованием текущего или переданного языкового стандарта. Есть более безопасные версии этих функций. См. раздел [Функции strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** и **_mbstok_l** нельзя использовать в приложениях, которые выполняются в среда выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
char *strtok_l(
   char *strToken,
   const char *strDelimit,
   _locale_t locale
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
wchar_t *wcstok_l(
   wchar_t *strToken,
   const wchar_t *strDelimit,
   _locale_t locale
);
unsigned char *_mbstok(
   unsigned char *strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok_l(
   unsigned char *strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*strToken*<br/>
Строка, содержащая токен или токены.

*стрделимит*<br/>
Набор символов-разделителей.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий токен, найденный в *strToken*. Функции возвращают **значение NULL** , если больше не найдено маркеров. Каждый вызов изменяет *strToken* , подставив нуль-символ для первого разделителя, который находится после возвращаемого маркера.

## <a name="remarks"></a>Remarks

Функция **strtok** находит следующий токен в *strToken*. Набор символов в *стрделимит* указывает возможные разделители токена, которые должны быть найдены в *strToken* в текущем вызове. **wcstok** и **_mbstok** — это версии **strtok**для расширенных символов и многобайтовых символов. Аргументы и возвращаемое значение **wcstok** являются строками расширенных символов. **_mbstok** являются строками многобайтовых символов. В остальном эти три функции ведут себя идентично.

> [!IMPORTANT]
> Эти функции представляют потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

При первом вызове функции **strtok**функция пропускает ведущие разделители и возвращает указатель на первый маркер в *strToken*, завершая маркер символом NULL. Дополнительные маркеры можно разделить из оставшейся части *strToken* на серию вызовов **strtok**. Каждый вызов **strtok** изменяет *strToken* , вставляя символ NULL после **маркера** , возвращенного этим вызовом. Чтобы считать следующий токен из *strToken*, вызовите **strtok** со значением **null** для аргумента *strToken* . Аргумент *StrToken* **со значением NULL** приводит к тому, что **strtok** ищет следующий токен в измененном *strToken*. Аргумент *стрделимит* может принимать любое значение от одного вызова к следующему, чтобы набор разделителей мог различаться.

На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md).

Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. Версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> Каждая функция использует статическую локальную в потоке переменную для разбора строки на токены. Поэтому эти функции могут вызвать одновременно несколько потоков без нежелательных последствий. Однако в пределах одного потока чередование вызовов одной из этих функций с большой степенью вероятности приводит к повреждению данных и получению неточных результатов. При синтаксическом анализе разных строк сначала завершите анализ одной строки, а затем начинайте анализ следующей. Кроме того, помните о потенциальной опасности, возникающей при вызове одной из этих функций из цикла, в котором также вызывается другая функция. Если другая функция использует одну из этих функций, произойдет чередование последовательностей вызовов, что приведет к повреждению данных.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtok**|\<string.h>|
|**wcstok**|\<string.h> или \<wchar.h>|
|**_mbstok**, **_mbstok_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
