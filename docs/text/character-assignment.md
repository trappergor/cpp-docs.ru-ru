---
title: Присваивание символов
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 88c42435d336ba78e87c9acfe3ada5fddbd18fb8
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750706"
---
# <a name="character-assignment"></a>Присваивание символов

Рассмотрим следующий пример, в котором **хотя** цикл проверяет строку, копируя все символы, кроме «X» в другую строку:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

Код копирует байт с `sz2` в расположении, указанном `sz1`, затем увеличивает `sz1` получать следующий байт. Однако, если следующий символ в `sz2` — это двухбайтовый символ, назначение `sz1` копируется только первый байт. В следующем коде используется переносимой функция для безопасного копирования символа, а другой для увеличения `sz1` и `sz2` правильно:

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

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)<br/>
[Сравнение знаков](../text/character-comparison.md)
