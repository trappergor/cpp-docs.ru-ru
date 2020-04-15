---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Описывает _mbclen, mblen, _mblen_l и _mbclen_l функций библиотеки Microsoft C Runtime Library (CRT).
ms.date: 4/2/2020
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
- _o__mbclen
- _o__mbclen_l
- _o__mblen_l
- _o_mblen
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
ms.openlocfilehash: 76e8771898d8baa65f275304a9aefdcaeeb5b3bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341125"
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

*C*\
Многобайтовый символ.

*mbstr*\
Адрес последовательности байтов (многобайтовый символ).

*Рассчитывать*\
Число проверяемых байтов.

*Языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbclen** и **_mbclen_l** вернуть 1 или 2, в зависимости от длины мультибайтного символа *c*. Функции всегда возвращают 1 для UTF-8, будь то *c* мультибайт или нет. Для возврата ошибок для **_mbclen**нет возврата ошибок.

Если *mbstr* не **является NULL,** **mblen** и **_mblen_l** вернуть длину, в байтах, мультибайтного символа. Функции **mblen** и **_mblen_l** работают правильно на UTF-8 и могут вернуть значение между 1 и 3. Когда *mbstr* **null** (или он указывает на широкохарактерный нулевой характер), **mblen** и **_mblen_l** вернуть 0. Объект, на который указывает *mbstr,* должен сформировать действительный мультибайтовый символ в пределах символов первого *счета,* или **mblen** и **_mblen_l** возврат -1.

## <a name="remarks"></a>Remarks

Функция **_mbclen** возвращает длину, в байтах, мультибайтного символа *c*. Если *c* не указывает на свинец байт мультибайтного персонажа (определяемого неявным призывом к [_ismbblead,](ismbblead-ismbblead-l.md)результат **_mbclen** непредсказуем.

**mblen** возвращает длину байтов *mbstr,* если это действительный мультибайтовый символ. Он также определяет достоверность мультибайт-символа, связанную со страницей кода. **mblen** рассматривает *количество* или меньше байтов, содержащихся в *mbstr,* но не более **MB_CUR_MAX** байтов.

Значение вывода зависит от LC_CTYPE **параметра** категории локализовать. Версии этих функций без **_l** суффикса используют текущий локали для этого поведения, зависящем от локали. Суффиксированные версии **_l** ведут себя одинаково, но вместо этого используют параметр локализации, передаваемый. Для получения дополнительной информации см. [Setlocale](setlocale-wsetlocale.md) и [Locale](../../c-runtime-library/locale.md).

**_mbclen,** **_mblen_l**и **_mbclen_l** являются специфичными для Корпорации Майкрософт, а не частью библиотеки Standard C. Мы не рекомендуем вам использовать их там, где вам нужен портативный код. Для совместимости Standard C используйте **mblen** или **mbrlen** вместо этого.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Сопоставляется макросу или встраиваемой функции|**_mbclen**|Сопоставляется макросу или встраиваемой функции|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)\
[Языкового стандарта](../../c-runtime-library/locale.md)\
[Интерпретация последовательностей мультибайт-символа](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[мбрлен](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
