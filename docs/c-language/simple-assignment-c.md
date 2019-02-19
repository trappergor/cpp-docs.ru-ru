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
ms.openlocfilehash: 77c61101e9540a0d9469e7176eb15992a73b4b09
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148976"
---
# <a name="simple-assignment-c"></a>Простое назначение (C)

Оператор простого присваивания присваивает значение правого операнда левому операнду. Значения правого операнда преобразуется в тип выражения присваивания и заменяет значение, хранящееся в объекте, определяемом левым операндом. Применяются правила преобразования для назначений (см. статью [Преобразования назначений](../c-language/assignment-conversions.md)).

```
double x;
int y;

x = y;
```

В этом примере значение переменной `y` преобразуется в тип **double** и присваивается переменной `x`.

## <a name="see-also"></a>См. также

[Операторы присваивания C](../c-language/c-assignment-operators.md)
