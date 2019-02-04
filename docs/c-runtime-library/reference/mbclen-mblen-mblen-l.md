---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
apiname:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
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
ms.openlocfilehash: b7888b0b8c87a632dcbb63f54ade11080c7a309a
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702964"
---
# <a name="mbclen-mblen-mblenl-mbclenl"></a>_mbclen, mblen, _mblen_l, _mbclen_l

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

*mbstr*<br/>
Адрес последовательности байтов (многобайтовый символ).

*count*<br/>
Число проверяемых байтов.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbclen** возвращает 1 или 2, в соответствии с, следует ли Многобайтовый символ *c* 1 или 2 байта. Отсутствуют ошибки, возвращаемое для **_mbclen**. Если *mbstr* не **NULL**, **mblen** возвращает длину в байтах, многобайтового символа. Если *mbstr* — **NULL** или указывает на нуль-символ Юникода, **mblen** возвращает 0. При объекта, *mbstr* точек не образует допустимый Многобайтовый символ в первых *число* символов, **mblen** возвращает -1.

## <a name="remarks"></a>Примечания

**_Mbclen** функция возвращает длину в байтах, многобайтового символа *c*. Если *c* не указывает на старший байт многобайтового символа, как определяется неявный вызов **_ismbblead**, результат **_mbclen** непредсказуем.

**mblen** возвращает длину в байтах *mbstr* Если это допустимый Многобайтовый символ и определяет допустимость многобайтовых символов в соответствии с кодовой страницей. **mblen** проверяет *число* или меньшее число байтов, содержащихся в *mbstr*, но не более чем **MB_CUR_MAX** байт.

Выходное значение зависит от **LC_CTYPE** категории языкового стандарта; см. описание [setlocale](setlocale-wsetlocale.md) Дополнительные сведения. В версиях этих функций без **_l** суффикс используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта. **_L** суффиксами версии работают так же, но они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
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
