---
title: Символ назначения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e17ace90abef63ce4af1dd56b5bbe8dfed9510c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429556"
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