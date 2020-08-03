---
title: Простое назначение (C)
ms.date: 11/04/2016
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
ms.openlocfilehash: 64112a54828a9a6626e78e556e8fe6dc52a3300f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229549"
---
# <a name="simple-assignment-c"></a>Простое назначение (C)

Оператор простого присваивания присваивает значение правого операнда левому операнду. Значения правого операнда преобразуется в тип выражения присваивания и заменяет значение, хранящееся в объекте, определяемом левым операндом. Применяются правила преобразования для назначений (см. статью [Преобразования назначений](../c-language/assignment-conversions.md)).

```
double x;
int y;

x = y;
```

В этом примере значение переменной `y` преобразуется в тип **`double`** и присваивается переменной `x`.

## <a name="see-also"></a>См. также

[Операторы присваивания C](../c-language/c-assignment-operators.md)
