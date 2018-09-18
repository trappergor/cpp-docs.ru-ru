---
title: Использование операторов сложения | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 050db08d00d79e3cfee0ab7549532d78a51b1ade
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078872"
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

Значение `i` умножается на длину типа **float** и добавляется к `&x[4]`. Результирующее значение указателя является адресом `x[8]`.

```
j = &x[i] - &x[i-2];
```

В этом примере адрес третьего элемента `x` (заданного `x[i-2]`) вычитается из адреса пятого элемента `x` (заданного `x[i]`). Разница делится на длину типа **float**; результатом является целочисленное значение 2.

## <a name="see-also"></a>См. также

[Аддитивные операторы в C](../c-language/c-additive-operators.md)