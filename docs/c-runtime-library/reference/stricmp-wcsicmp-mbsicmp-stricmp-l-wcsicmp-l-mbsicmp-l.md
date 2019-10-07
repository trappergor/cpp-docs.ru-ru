---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 11/04/2016
api_name:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
ms.openlocfilehash: 108a3c572174be5048d0bba48a4da0f4a735f458
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940683"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Выполняет сравнение строк без учета регистра.

> [!IMPORTANT]
> **_mbsicmp** и **_mbsicmp_l** нельзя использовать в приложениях, которые выполняются в среда выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*строка1*, *строка2*<br/>
Строки с завершающим нулем для сравнения.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение указывает отношение *строка1* к *строка2* следующим образом.

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*строка1* меньше, чем *строка2*|
|0|*строка1* совпадает с *строка2*|
|> 0|*строка1* больше, чем *строка2*|

При возникновении ошибки **_mbsicmp** возвращает **_NLSCMPERROR**, который определен в \<String. h > и \<mbstring. h >.

## <a name="remarks"></a>Примечания

Функция **_stricmp** по порядковому номеру сравнивает символы *строка1* и *строка2* после преобразования каждого символа в нижний регистр и возвращает значение, указывающее их связь. **_stricmp** отличается от **_stricoll** тем, что сравнение **_stricmp** затрагивает только **LC_CTYPE**, который определяет, какие символы являются прописными и строчными. Функция **_stricoll** сравнивает строки в соответствии с категориями **LC_CTYPE** и **LC_COLLATE** языкового стандарта, включая регистр и порядок сортировки. Дополнительные сведения о категории **LC_COLLATE** см. в статье категории [setlocale](setlocale-wsetlocale.md) и [языкового стандарта](../../c-runtime-library/locale-categories.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для поведения, зависящего от языкового стандарта. Версии с суффиксом идентичны за исключением того, что вместо этого они используют переданный языковой стандарт. Если языковой стандарт не задан, используется языковой стандарт C. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** эквивалентен **_strcmpi**. Они могут быть взаимозаменяемы, но **_stricmp** является предпочтительным стандартом.

Функция **_strcmpi** эквивалентна **_stricmp** и предоставляется только для обратной совместимости.

Так как **_stricmp** выполняет сравнение в нижнем регистре, это может привести к непредвиденному поведению.

Чтобы продемонстрировать, когда преобразование регистра с помощью **_stricmp** влияет на результат сравнения, предположим, что у вас есть две строки Джонстон и JOHN_HENRY. Строка JOHN_HENRY будет считаться меньше JOHNSTON, так как "_" имеет меньшее значение ASCII, чем s в нижнем регистре. На самом деле любой символ, имеющий значение ASCII в диапазоне от 91 до 96, считается меньше любой буквы.

Если вместо **_stricmp**используется функция [strcmp](strcmp-wcscmp-mbscmp.md) , JOHN_HENRY будет больше Джонстон.

**_wcsicmp** и **_mbsicmp** — это версии **_stricmp**для расширенных символов и многобайтовых символов. Аргументы и возвращаемое значение **_wcsicmp** являются строками расширенных символов. **_mbsicmp** являются строками многобайтовых символов. **_mbsicmp** распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает **_NLSCMPERROR** при возникновении ошибки. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). В остальном эти три функции ведут себя идентично.

поведение **_wcsicmp** и **wcscmp** идентично, за исключением того, что **wcscmp** не преобразует свои аргументы в нижний регистр перед их сравнением. поведение **_mbsicmp** и **_mbscmp** идентично, за исключением того, что **_mbscmp** не преобразует свои аргументы в нижний регистр перед их сравнением.

Для работы с символами латиницы 1 необходимо вызвать [setlocale](setlocale-wsetlocale.md) для **_wcsicmp** . Язык C действует по умолчанию, поэтому, например, ä не будет сравниваться со значением Ä. Вызовите **setlocale** с любым языковым стандартом, отличным от локали языка C, до вызова **_wcsicmp**. В следующем примере показано, как **_wcsicmp** зависит от языкового стандарта:

```C
// crt_stricmp_locale.c
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

Альтернативой является вызов [_create_locale, _wcreate_locale](create-locale-wcreate-locale.md) и передача возвращенного объекта локали в качестве параметра в **_wcsicmp_l**.

Все эти функции проверяют свои параметры. Если либо *строка1* , либо *строка_замены* являются пустыми указателями, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции возвращают **_NLSCMPERROR** и применяют **значение "** **еинвал**".

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> или \<wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
