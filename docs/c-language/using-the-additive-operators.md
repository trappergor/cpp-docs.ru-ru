---
title: Использование операторов сложения
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
ms.openlocfilehash: 06d71f3ad1944976a8d415be9487cb5ea365fa26
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213688"
---
# <a name="using-the-additive-operators"></a>Использование операторов сложения

В следующих примерах, иллюстрирующих операторы сложения и вычитания, используются следующие объявления.

```
int i = 4, j;
float x[10];
float *px;
```

Эти операторы эквивалентны.

```
px = &x[4 + i];
px = &x[4] + i;
```

Значение `i` умножается на длину типа **`float`** и добавляется к `&x[4]`. Результирующее значение указателя является адресом `x[8]`.

```
j = &x[i] - &x[i-2];
```

В этом примере адрес третьего элемента `x` (заданного `x[i-2]`) вычитается из адреса пятого элемента `x` (заданного `x[i]`). Разница делится на длину типа **`float`** ; результатом является целочисленное значение 2.

## <a name="see-also"></a>См. также

[Аддитивные операторы в C](../c-language/c-additive-operators.md)
