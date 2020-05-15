---
title: Диапазон значений типа char
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 8cb2609aca910056b5243fddc868710581e576e7
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480907"
---
# <a name="range-of-char-values"></a>Диапазон значений типа char

**ANSI 3.2.1.1** Имеет ли "простой" тип **char** тот же диапазон значений, что и **signed char** или **unsigned char**

Все знаковые значения char находятся в диапазоне от –128 до 127. Все беззнаковые значения char находятся в диапазоне от 0 до 255.

Параметр компилятора [`/J`](../build/reference/j-default-char-type-is-unsigned.md) меняет тип по умолчанию для **char** с **signed char** на **unsigned char**.

## <a name="see-also"></a>См. также

[Символы](../c-language/characters.md)
