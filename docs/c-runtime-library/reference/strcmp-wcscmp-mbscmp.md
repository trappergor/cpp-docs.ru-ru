---
title: strcmp, wcscmp, _mbscmp, _mbscmp_l
ms.date: 4/2/2020
api_name:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
- _o__mbscmp
- _o__mbscmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: 16bb294f7bbdc0b95b59b845d7b714f823f9d962
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357288"
---
# <a name="strcmp-wcscmp-_mbscmp-_mbscmp_l"></a>strcmp, wcscmp, _mbscmp, _mbscmp_l

Сравнивают строки.

> [!IMPORTANT]
> **_mbscmp** и **_mbscmp_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*string1*, *string2*<br/>
Строки с завершающим нулем для сравнения.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Значение возврата для каждой из этих функций указывает на обыданное отношение *строки1* к *string2.*

|Значение|Отношение string1 к string2|
|-----------|----------------------------------------|
|< 0|*string1* меньше, чем *string2*|
|0|*string1* идентичен *string2*|
|> 0|*string1* больше, чем *string2*|

По ошибке проверки параметра, **_mbscmp** и **_mbscmp_l** возврата **_NLSCMPERROR,** который определяется в \<> строки и \<mbstring.h>.

## <a name="remarks"></a>Remarks

Функция **strcmp** выполняет ординальное сравнение *string1* и *string2* и возвращает значение, указывавщее их связь. **wcscmp** и **_mbscmp,** соответственно, широкохарактерные и многобайт-символверсии **strcmp**. **_mbscmp** распознает последовательности мультибайт-символов в соответствии с текущей многобайтной страницей кода и возвращает **_NLSCMPERROR** ошибки. **_mbscmp_l** имеет то же поведение, но использует параметр локализации, который передается в вместо текущего локализации. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). Кроме того, если *string1* или *string2* является нулевой указателем, **_mbscmp** вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **_mbscmp** и **_mbscmp_l** **вернуться _NLSCMPERROR** и установить **errno** в **EINVAL**. **strcmp** и **wcscmp** не проверяют их параметры. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

Функции **strcmp** отличаются от функций **strcoll** в том, что сравнения **strcmp** являются ординаальными, и не зависят от локаль. **strcoll** сравнивает строки лексикографически, используя **LC_COLLATE** категорию текущего локализации. Для получения дополнительной информации о **категории LC_COLLATE** см. [setlocale, _wsetlocale](setlocale-wsetlocale.md).

В языковом стандарте "C" порядок символов в наборе символов (набор символов ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу ä (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.

В лоцах, для которых отличается набор символов и порядок лексикографических символов, можно использовать **strcoll** вместо **strcmp** для лексикографического сравнения строк. Кроме того, можно использовать **strxfrm** на исходных строках, а затем использовать **strcmp** на результирующих строках.

Функции **strcmp** чувствительны к случаям. stricmp, ** \_wcsicmp**, и ** \_mbsicmp** сравнить строки, сначала преобразовывая их в их нижних форм. ** \_** Две строки, содержащие символы, расположенные между «я» и «а» в таблице\\ASCII (', ',', '', '', '' и ')\`сравниваются по-разному, в зависимости от их случая. Например, две строки "ABCDE" и "ABCD" сравнивают один способ, если сравнение является нижним регистром ("abcde" > "abcd") и в другую сторону ("ABCDE" < "ABCD") если сравнение является верхним регистром.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strcmp**|\<string.h>|
|**wcscmp**|\<string.h> или \<wchar.h>|
|**_mbscmp**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
