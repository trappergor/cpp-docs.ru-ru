---
title: alignof и alignas (C++)
ms.date: 11/04/2016
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
ms.openlocfilehash: e5d023d7969764bdd36030a508abdd94068e48b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493656"
---
# <a name="alignof-and-alignas-c"></a>alignof и alignas (C++)

**Alignas** спецификатор типа — это стандартный способ переносимый C++ для задания настраиваемого выравнивания переменных и определяемых пользователем типов. **Alignof** оператор — аналогичен стандартному переносимому способу получения выравнивания указанного типа или переменной.

## <a name="example"></a>Пример

Можно использовать **alignas** для класса, прохода или объединения, или для отдельных членов. Когда несколько **alignas** спецификаторы встречаются, компилятор выберет наиболее строгом тот (один с наибольшим значением).

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>См. также

[Выравнивание](../cpp/alignment-cpp-declarations.md)