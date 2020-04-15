---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 4/2/2020
api_name:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
- _o__mbsicmp
- _o__mbsicmp_l
- _o__stricmp
- _o__stricmp_l
- _o__wcsicmp
- _o__wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
ms.openlocfilehash: 315a86c5cf7e58219bad25f2b6633dd91275c09f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320469"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Выполняет сравнение строк без учета регистра.

> [!IMPORTANT]
> **_mbsicmp** и **_mbsicmp_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
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

Значение возврата указывает на отношение *строки1* к *string2* следующим образом.

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*string1* меньше, чем *string2*|
|0|*строка1* идентична *строке2*|
|> 0|*string1* больше, чем *string2*|

При ошибке **_mbsicmp** возвращает **_NLSCMPERROR,** \<который определяется \<в> строки и> mbstring.h.

## <a name="remarks"></a>Remarks

**Функция _stricmp** обычно сравнивает *string1* и *string2* после преобразования каждого символа в нижний регистр и возвращает значение, указывающее на их связь. **_stricmp** отличается от **_stricoll** тем, что сравнение **_stricmp** зависит только от **LC_CTYPE,** который определяет, какие символы являются верхним и нижним регистром. Функция **_stricoll** сравнивает строки в соответствии с **LC_CTYPE** и **LC_COLLATE** категориями локализу, который включает как случай, так и порядок сопоставления. Для получения дополнительной информации о **категории LC_COLLATE** [см.](setlocale-wsetlocale.md) [Locale Categories](../../c-runtime-library/locale-categories.md) Версии этих функций без **_l** суффикса используют текущий локали для поведения, зависящем от локализации. Версии с суффиксом идентичны за исключением того, что вместо этого они используют переданный языковой стандарт. Если языковой стандарт не задан, используется языковой стандарт C. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** эквивалентен **_strcmpi.** Они могут быть использованы взаимозаменяемы, но **_stricmp** является предпочтительным стандартом.

Функция **_strcmpi** эквивалентна **_stricmp** и предусмотрена только для обратной совместимости.

Поскольку **_stricmp** делает сравнения в нижнем регистре, это может привести к неожиданному поведению.

Чтобы проиллюстрировать, когда преобразование случая по **_stricmp** влияет на результат сравнения, предположим, что у вас есть две строки JOHNSTON и JOHN_HENRY. Строка JOHN_HENRY будет считаться меньше JOHNSTON, так как "_" имеет меньшее значение ASCII, чем s в нижнем регистре. На самом деле любой символ, имеющий значение ASCII в диапазоне от 91 до 96, считается меньше любой буквы.

Если функция [strcmp](strcmp-wcscmp-mbscmp.md) используется вместо **_stricmp,** JOHN_HENRY будет больше, чем JOHNSTON.

**_wcsicmp** и **_mbsicmp** являются широкохарактерными и многобайтными версиями **_stricmp.** Аргументы и значение возврата **_wcsicmp** являются широкохарактерными строками; _mbsicmp **являются** многобайтными строками. **_mbsicmp** распознает последовательности мультибайт-символов в соответствии с текущей многобайтной страницей кода и возвращает **_NLSCMPERROR** по ошибке. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). В остальном эти три функции ведут себя идентично.

**_wcsicmp** и **wcscmp** ведут себя одинаково, за исключением того, что **wcscmp** не преобразует свои аргументы в более низкий регистр, прежде чем сравнивать их. **_mbsicmp** и **_mbscmp** ведут себя одинаково, за исключением того, что **_mbscmp** не преобразует свои аргументы в более низкий регистр, прежде чем сравнивать их.

Вам нужно будет вызвать [setlocale](setlocale-wsetlocale.md) для **_wcsicmp** для работы с латинскими 1 символами. Локаль C действует по умолчанию, так что, например, не будет сравниваться с «. Call **setlocale** с любым локаль, кроме C locale до вызова **_wcsicmp.** Следующий пример показывает, насколько **_wcsicmp** чувствителен к локалю:

```C
// crt_stricmp_locale.c
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

Альтернативой является вызов [_create_locale, _wcreate_locale](create-locale-wcreate-locale.md) и передать возвращенный объект локального в качестве параметра **_wcsicmp_l.**

Все эти функции проверяют свои параметры. Если *строка1* или *строка2* являются нулевыми указатели, недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции возвращают **_NLSCMPERROR** и установить **errno** к **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> или \<wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_stricmp.c

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
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
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
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
