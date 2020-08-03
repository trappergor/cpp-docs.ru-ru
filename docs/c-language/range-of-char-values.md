---
title: Диапазон значений типа char
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 085f7a319cb193f9d9d744d6e896062e550404cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227807"
---
# <a name="range-of-char-values"></a>Диапазон значений типа char

**ANSI 3.2.1.1** Имеет ли "простой" тип **`char`** тот же диапазон значений, что и **`signed char`** или **`unsigned char`**

Все знаковые значения char находятся в диапазоне от –128 до 127. Все беззнаковые значения char находятся в диапазоне от 0 до 255.

Параметр компилятора [`/J`](../build/reference/j-default-char-type-is-unsigned.md) указывает, что для **`char`** по умолчанию вместо **`signed char`** будет использоваться **`unsigned char`** .

## <a name="see-also"></a>См. также

[Символы](../c-language/characters.md)
