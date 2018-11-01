---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: 5fc27c7f1dfde7d1f686f0a752652773ade9cc0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464068"
---
# <a name="false-c"></a>false (C++)

Ключевое слово является одним из двух значений переменной типа [bool](../cpp/bool-cpp.md) или условного выражения (условное выражение теперь является **true** логическое выражение). Например если `i` является переменной типа **bool**, `i = false;` оператор назначает **false** для `i`.

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

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)