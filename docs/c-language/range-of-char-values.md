---
title: Диапазон значений типа char
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 8cb2609aca910056b5243fddc868710581e576e7
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480907"
---
# <a name="range-of-char-values"></a>Диапазон значений типа char

**ANSI 3.2.1.1.1** Имеет ли "обычный" **символ** такой же диапазон значений, как **подписанный символ** или **неподписанный символ**

Все знаковые значения char находятся в диапазоне от –128 до 127. Все беззнаковые значения char находятся в диапазоне от 0 до 255.

Опция [`/J`](../build/reference/j-default-char-type-is-unsigned.md) компилятора изменяет тип по умолчанию для **символа** с **подписанного символа** на **неподписанный символ.**

## <a name="see-also"></a>См. также

[Символов](../c-language/characters.md)
