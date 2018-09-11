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
ms.openlocfilehash: 61d92c02c4410bdc01b76ac6307fb9bb2652880a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203612"
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

Если **wctob** успешно преобразует строку расширенных символов, он возвращает соответствующее представление многобайтового символа, только в том случае, если Многобайтовый символ имеет длину ровно один байт. Если **wctob** встречает расширенный символ, не может преобразовать Многобайтовый или Многобайтовый символ отлично от один байт, он возвращает значение -1.

## <a name="remarks"></a>Примечания

**Wctob** функция преобразует строку расширенных символов, содержащихся в *wchar* соответствующий Многобайтовый символ, передаваемый возвращаемым **int** значение, если многобайтовой символ имеет длину ровно один байт.

Если **wctob** завершилась неудачно и соответствующий Многобайтовый символ найден, функция задает **errno** для **EILSEQ** и возвращает – 1.

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
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
