---
title: Присваивание символов
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 0f627f88ca2b1d3533d3690cd0316ee047a327ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217315"
---
# <a name="character-assignment"></a>Присваивание символов

Рассмотрим следующий пример, в котором **`while`** цикл сканирует строку, копируя все символы, кроме "X", в другую строку:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

Код копирует байт в `sz2` расположение, на которое указывает `sz1` , затем увеличивает `sz1` значение, чтобы получить следующий байт. Но если следующий символ в `sz2` является двухбайтовым символом, то присваивание `sz1` копирует только первый байт. В следующем коде переносимая функция используется для безопасного копирования символа, а другой — для `sz1` его `sz2` правильного увеличения.

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
    {
        _mbscpy_s( sz1, 1, sz2 );
        sz1 = _mbsinc( sz1 );
        sz2 = _mbsinc( sz2 );
    }
    else
        sz2 = _mbsinc( sz2 );
}
```

## <a name="see-also"></a>См. также раздел

[Советы по программированию многобайтовых кодировок](../text/mbcs-programming-tips.md)<br/>
[Сравнение символов](../text/character-comparison.md)
