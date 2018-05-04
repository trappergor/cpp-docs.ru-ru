---
title: wctob | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wctob
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctob
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cff2dcb8d6b0ad3756a8a0047fcc9b982fb7bb8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="wctob"></a>wctob

Определяет, соответствует ли расширенный символ многобайтовому символу, и возвращает его представление в многобайтовой кодировке.

## <a name="syntax"></a>Синтаксис

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Параметры

*wchar*<br/>
Значение, которое необходимо преобразовать.

## <a name="return-value"></a>Возвращаемое значение

Если **wctob** успешно преобразует расширенный символ, он возвращает соответствующее представление многобайтовой только в том случае, если Многобайтовый символ имеет длину ровно один байт. Если **wctob** встречает расширенный символ, не может преобразовать Многобайтовый символ или Многобайтовый символ отлично от один байт, возвращается значение -1.

## <a name="remarks"></a>Примечания

**Wctob** функция преобразует расширенный символ, содержащийся в *wchar* в соответствующий Многобайтовый символ, передаваемый возвращаемым **int** значение, если многобайтовой символ имеет длину ровно один байт.

Если **wctob** завершилась неудачно и соответствующий Многобайтовый символ найден, функция задает **errno** для **EILSEQ** и возвращает значение -1.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение **wcstombs** функции.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}

```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
