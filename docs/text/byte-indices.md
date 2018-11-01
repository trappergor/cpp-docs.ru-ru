---
title: Индексы байтов
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 4e19868e5297e1c1615efabde2aee418bc53c51e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448819"
---
# <a name="byte-indices"></a>Индексы байтов

Следуйте приведенным ниже советам:

- Работа с побайтовым индекса в строку создает проблемы, похожие на те сформулированный работу с указателем. Рассмотрим следующий пример, который проверяет строку на наличие символа обратной косой черты.

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   Это может быть индексом младший байт, не старшим байтом, и поэтому не может указывать на `character`.

- Используйте [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) функция устранены выше:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   Это правильно индексирует старшим байтом, поэтому для `character`. `_mbclen` Функция определяет размер символа (1 или 2 байта).

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)<br/>
[Последний символ в строке](../text/last-character-in-a-string.md)