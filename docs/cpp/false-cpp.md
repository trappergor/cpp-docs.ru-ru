---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: d6162bdde3dea0d245a0c83c1d52b06003fee16c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227495"
---
# <a name="false-c"></a>false (C++)

Ключевое слово является одним из двух значений для переменной типа [bool](../cpp/bool-cpp.md) или условного выражения (условное выражение теперь является **`true`** логическим выражением). Например, если `i` является переменной типа **`bool`** , `i = false;` оператор присваивает значение **`false`** `i` .

## <a name="example"></a>Пример

```cpp
// bool_false.cpp
#include <stdio.h>

int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
