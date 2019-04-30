---
title: Индексы байтов
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5305a977c23d7a978a89c84809cc6fab8c5731eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410727"
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
