---
title: Переполнение буфера
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 71877ed770384190cb7f856567d9e7e845e3da19
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217328"
---
# <a name="buffer-overflow"></a>Переполнение буфера

Различные размеры символов могут вызвать проблемы при помещении символов в буфер. Рассмотрим следующий код, который копирует символы из строки в `sz` буфер `rgch` :

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

Вопрос: был ли последний байт скопирован в старший байт? Следующее не решает проблему, так как может привести к переполнению буфера:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy`Вызов пытается выполнить нужное действие — Скопируйте полный символ, будь то 1 или 2 байта. Но при этом не учитывается, что последний скопированный символ может не уместиться в буфере, если он имеет ширину 2 байта. Правильное решение:

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Этот код проверяет возможное переполнение буфера в тесте цикла, используя `_mbclen` для проверки размера текущего символа, на который указывает `sz` . Вызвав `_mbsnbcpy` функцию, можно заменить код в **`while`** цикле одной строкой кода. Пример:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>См. также раздел

[Советы по программированию многобайтовых кодировок](../text/mbcs-programming-tips.md)
