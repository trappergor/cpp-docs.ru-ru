---
title: Ошибка компилятора C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 94f35f9f3bf64e09087f28a11a4fb9802d9d3c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761521"
---
# <a name="compiler-error-c3540"></a>Ошибка компилятора C3540

"тип": sizeof нельзя применить к типу, содержащему "Auto"

Оператор [sizeof](../../cpp/sizeof-operator.md) нельзя применить к указанному типу, так как он содержит описатель `auto`.

## <a name="example"></a>Пример

В следующем примере выдается C3540.

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[Оператор sizeof](../../cpp/sizeof-operator.md)
