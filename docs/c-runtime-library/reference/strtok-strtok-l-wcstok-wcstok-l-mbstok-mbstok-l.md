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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d228d9824c534a21e4a22797e4b070e6d8d0b179
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365199"
---
# <a name="strtok-_strtok_l-wcstok-_wcstok_l-_mbstok-_mbstok_l"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Находят следующий токен в строке с использованием текущего или переданного языкового стандарта. Есть более безопасные версии этих функций. См. раздел [Функции strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** и **_mbstok_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*strToToken*<br/>
Строка, содержащая токен или токены.

*strDelimit*<br/>
Набор символов-разделителей.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий маркер, найденный в *strToken.* Функции возвращают **NULL,** когда больше не найдено токенов. Каждый вызов изменяет *strToken,* заменяя нулевой символ для первого делимитера, который происходит после возвращенного токена.

## <a name="remarks"></a>Remarks

Функция **strtok** находит следующий маркер в *strToken.* Набор символов в *strDelimit* определяет возможные делимитеры токена, которые можно найти в *strToken* на текущем вызове. **wcstok** и **_mbstok** широкохарактерные и мультибайт-символверсии **стритока.** Аргументы и значение возврата **wcstok** являются широкохарактерные строки; _mbstok **являются** многобайтными строками. В остальном эти три функции ведут себя идентично.

> [!IMPORTANT]
> Эти функции представляют потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

При первом вызове на **strtok**функция пропускает ведущие делимитемые и возвращает указатель на первый маркер в *strToken,* прекращая токен с нулевым характером. Больше токенов может быть разбито из оставшейся *части strToken* серией вызовов **на strtok.** Каждый вызов **strtok** изменяет *strToken* путем вставки нулевого символа после того, как **маркер** вернулся этим вызовом. Чтобы прочитать следующий маркер из *strToken,* позвоните **в strtok** со значением **NULL** для аргумента *strToken.* Аргумент **NULL** *strToken* вызывает **сток** для поиска следующего маркера в модифицированном *strToken.* Аргумент *strDelimit* может принимать любое значение от одного вызова к другому, так что набор делимитеров может меняться.

Значение вывода зависит от настройки **LC_CTYPE** категории локализуем локализовать. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md).

Версии этих функций без **_l** суффикса используют текущий локали для этого поведения, зависящем от локали. Версии с **_l** суффикса идентичны, за исключением того, что они используют параметр локализации, пройденном вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> Каждая функция использует статическую локальную в потоке переменную для разбора строки на токены. Поэтому эти функции могут вызвать одновременно несколько потоков без нежелательных последствий. Однако в пределах одного потока чередование вызовов одной из этих функций с большой степенью вероятности приводит к повреждению данных и получению неточных результатов. При синтаксическом анализе разных строк сначала завершите анализ одной строки, а затем начинайте анализ следующей. Кроме того, помните о потенциальной опасности, возникающей при вызове одной из этих функций из цикла, в котором также вызывается другая функция. Если другая функция использует одну из этих функций, произойдет чередование последовательностей вызовов, что приведет к повреждению данных.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
