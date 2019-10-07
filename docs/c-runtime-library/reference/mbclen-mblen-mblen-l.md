---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 96775f513b33eb407981480c17cb609dd85383f6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952565"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Получает длину многобайтового символа и определяет его допустимость.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Многобайтовый символ.

*мбстр*<br/>
Адрес последовательности байтов (многобайтовый символ).

*count*<br/>
Число проверяемых байтов.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbclen** возвращает 1 или 2 в соответствии с длиной многобайтового символа *c* — 1 или 2 байта. Для **_mbclen**не возвращается ошибка. Если *мбстр* не **равно NULL**, **mblen** возвращает длину многобайтового символа в байтах. Если *мбстр* имеет **значение NULL** или указывает на символ в расширенных символах null, **mblen** возвращает 0. Если объект, на который указывает *мбстр* , не формирует допустимый многобайтовый символ в первых символах *Count* , **mblen** возвращает значение-1.

## <a name="remarks"></a>Примечания

Функция **_mbclen** возвращает длину многобайтового символа *c*в байтах. Если *c* не указывает на старший байт многобайтового символа, как определено неявным вызовом **_ismbblead**, результат **_mbclen** является непредсказуемым.

**mblen** возвращает длину в байтах *мбстр* , если это допустимый многобайтовый символ, и определяет допустимость многобайтовых символов, связанную с кодовой страницей. **mblen** проверяет *число* байтов, содержащихся в *Мбстр*, но не более **MB_CUR_MAX** байтов.

На выходное значение влияет настройка категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md) . Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. Версии с суффиксами **_l** ведут себя одинаково, но они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Сопоставляется макросу или встраиваемой функции|**_mbclen**|Сопоставляется макросу или встраиваемой функции|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
