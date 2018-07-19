---
title: Функции strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45e2155f830a302f316aa96ce41b65a71709bc0d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451801"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Находят следующий токен в строке с использованием текущего или переданного языкового стандарта. Есть более безопасные версии этих функций. См. раздел [Функции strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** и **_mbstok_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*strToken*<br/>
Строка, содержащая токен или токены.

*strDelimit*<br/>
Набор символов-разделителей.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий токен, найденный в *strToken*. Они возвращают **NULL** при нет больше токенов не найдено. Каждый вызов изменяет строку *strToken* путем замены символ null первый разделитель, находящийся после возвращенного токена.

## <a name="remarks"></a>Примечания

**Strtok** функция находит следующий токен в *strToken*. Набор символов в *strDelimit* указывает возможные разделители токенов, должно быть найдено в *strToken* во время текущего вызова. **wcstok** и **_mbstok** версии Юникода и многобайтовых символов **strtok**. Аргументы и возвращаемое значение **wcstok** являются двухбайтовые строки; аргументы **_mbstok** представляют собой строки многобайтовых символов. В остальном эти три функции ведут себя идентично.

> [!IMPORTANT]
> Эти функции представляют потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).

При первом вызове для **strtok**, функция пропускает ведущие разделители и возвращает указатель на первый токен в *strToken*, завершая токен нуль-символом. Можно выделить другие токены из оставшейся части *strToken* с помощью последовательных вызовов **strtok**. Каждый вызов **strtok** изменяет *strToken* , вставляя нуль-символ после **маркера** возвращенного этим вызовом. Чтобы прочитать следующий токен из *strToken*, вызовите **strtok** с **NULL** значение для *strToken* аргумент. **NULL** *strToken* аргумент причины **strtok** для поиска следующий токен в измененной *strToken*. *StrDelimit* аргумент может принимать любое значение от одного вызова к следующему, позволяя изменять набор разделителей.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> Каждая функция использует статическую локальную в потоке переменную для разбора строки на токены. Поэтому эти функции могут вызвать одновременно несколько потоков без нежелательных последствий. Однако в пределах одного потока чередование вызовов одной из этих функций с большой степенью вероятности приводит к повреждению данных и получению неточных результатов. При синтаксическом анализе разных строк сначала завершите анализ одной строки, а затем начинайте анализ следующей. Кроме того, помните о потенциальной опасности, возникающей при вызове одной из этих функций из цикла, в котором также вызывается другая функция. Если другая функция использует одну из этих функций, произойдет чередование последовательностей вызовов, что приведет к повреждению данных.

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

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
