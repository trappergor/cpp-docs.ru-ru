---
title: Переполнение буфера
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 7f9864e6b49446ea68d82e76e877ce9c677b893d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741378"
---
# <a name="buffer-overflow"></a>Переполнение буфера

Изменение размера знаков может вызвать проблемы при переводе символов в буфер. Рассмотрим следующий код, который копирует знаки из строки, `sz`, в буфер, `rgch`:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

Вопрос состоит в: Был последний байт старшим байтом? Следующее не решит проблему, так как существует потенциальная возможность переполнения буфера:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy` Пытается выполнить вызов — копирование полного знака, будь то 1 или 2 байта. Но он не принимает во внимание, что последний скопированный знак может не поместиться в буфер при символ занимает 2 байта. Правильным решением является:

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Этот код проверяет возможное переполнение буфера в цикле тестирования, с помощью `_mbclen` для тестирования размера текущего знака, на которые указывают `sz`. С помощью вызова `_mbsnbcpy` функции, вы можете заменить код в **хотя** цикла с помощью одной строки кода. Пример:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)
