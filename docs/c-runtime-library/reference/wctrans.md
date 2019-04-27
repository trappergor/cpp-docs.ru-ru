---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
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
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188459"
---
# <a name="wctrans"></a>wctrans

Определяет сопоставление одного набора кодов символов с другим.

## <a name="syntax"></a>Синтаксис

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>Параметры

*свойство*<br/>
Строка, указывающая одно из допустимых преобразований.

## <a name="return-value"></a>Возвращаемое значение

Если **LC_CTYPE** категории текущего языкового стандарта не определяет сопоставление, имя которого соответствует строке свойства *свойство*, функция возвращает нуль. В противном случае возвращается ненулевое значение, подходящее для использования в качестве второго аргумента последующего вызова [towctrans](towctrans.md).

## <a name="remarks"></a>Примечания

Эта функция определяет сопоставление одного набора кодов символов с другим.

Следующие пары вызовов действуют одинаково во всех языковых стандартах, но можно определить дополнительное сопоставление даже в языковом стандарте "C".

|Функция|Эквивалентно|
|--------------|-------------|
|ToLower(c)|towctrans (c, wctrans("towlower"))|
|towupper(c)|towctrans (c, wctrans("toupper"))|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
