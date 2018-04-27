---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
dev_langs:
- C++
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
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00678f8efc2a5c3b34fb3ba3f3d745f42174fd1d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Выполняет сравнение строк без учета регистра.

> [!IMPORTANT]
> **_mbsicmp** и **_mbsicmp_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*string1*, *строка2*<br/>
Строки с завершающим нулем для сравнения.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение отражает взаимосвязь *string1* для *string2* следующим образом.

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*string1* меньше, чем *строка2*|
|0|*string1* идентичен *строка2*|
|> 0|*string1* больше *строка2*|

При возникновении ошибки **_mbsicmp** возвращает **_NLSCMPERROR**, которая определена в \<string.h > и \<mbstring.h >.

## <a name="remarks"></a>Примечания

**_Stricmp** порядковым функция сравнивает *string1* и *string2* после преобразования каждого символа в регистре и возвращает значение, показывающее их взаимосвязь. **_stricmp** отличается от **_stricoll** в том, что **_stricmp** сравнения влияет только **LC_CTYPE**, которое определяет, какие символы в верхнем и в нижнем регистре. **_Stricoll** функция сравнивает строки в соответствии с **LC_CTYPE** и **LC_COLLATE** категории языкового стандарта, включая регистр и параметры сортировки порядок. Дополнительные сведения о **LC_COLLATE** категории, в разделе [setlocale](setlocale-wsetlocale.md) и [категории языкового стандарта](../../c-runtime-library/locale-categories.md). Версии этих функций без **_l** суффикс используют текущий языковой стандарт для поведения, зависящего от языкового стандарта. Версии с суффиксом идентичны за исключением того, что вместо этого они используют переданный языковой стандарт. Если языковой стандарт не задан, используется языковой стандарт C. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** эквивалентно **_strcmpi**. Они взаимозаменяемы, но **_stricmp** предпочтительнее стандарт.

**_Strcmpi** функция эквивалентна **_stricmp** и предоставляется только для обратной совместимости.

Поскольку **_stricmp** нижний регистр сравнения, это может привести к непредвиденному поведению.

Для иллюстрации того преобразование **_stricmp** влияет на результат сравнения, предположим, что две строки: JOHNSTON и JOHN_HENRY. Строка JOHN_HENRY будет считаться меньше JOHNSTON, так как "_" имеет меньшее значение ASCII, чем s в нижнем регистре. На самом деле любой символ, имеющий значение ASCII в диапазоне от 91 до 96, считается меньше любой буквы.

Если [strcmp](strcmp-wcscmp-mbscmp.md) функция используется вместо **_stricmp**, то JOHN_HENRY будет больше JOHNSTON.

**_wcsicmp** и **_mbsicmp** версии Юникода и многобайтовых символов **_stricmp**. Аргументы и возвращаемое значение **_wcsicmp** являются двухбайтовые строки; аргументы **_mbsicmp** представляют собой строки многобайтовых символов. **_mbsicmp** распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает **_NLSCMPERROR** при возникновении ошибки. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). В остальном эти три функции ведут себя идентично.

**_wcsicmp** и **wcscmp** ведут себя одинаково, за исключением того, что **wcscmp** не выполняет преобразование аргументов в нижний регистр перед их сравнением. **_mbsicmp** и **_mbscmp** ведут себя одинаково, за исключением того, что **_mbscmp** не выполняет преобразование аргументов в нижний регистр перед их сравнением.

Вам потребуется вызвать [setlocale](setlocale-wsetlocale.md) для **_wcsicmp** работать с символами Latin 1. По умолчанию действует языковой стандарт C, таким образом, например, ä не будет считаться равным Ä. Вызовите **setlocale** с любым языковым стандартом, отличным от C, перед вызовом **_wcsicmp**. Следующий пример демонстрирует, как **_wcsicmp** зависит от языкового стандарта:

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

Альтернативой является вызов [_create_locale _wcreate_locale](create-locale-wcreate-locale.md) и передать в качестве параметра для возвращаемого объекта языкового стандарта **_wcsicmp_l**.

Все эти функции проверяют свои параметры. Если параметр *string1* или *string2* — неопределенные указатели, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции возвращают **_NLSCMPERROR** и задайте **errno** для **EINVAL**.

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
