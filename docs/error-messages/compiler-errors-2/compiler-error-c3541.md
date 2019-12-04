---
title: Ошибка компилятора C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 1308ff91bcebabc5495b015321494f3457cf2d1e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761508"
---
# <a name="compiler-error-c3541"></a>Ошибка компилятора C3541

"тип": typeid нельзя применять к типу, содержащему "Auto"

Оператор [typeid](../../extensions/typeid-cpp-component-extensions.md) нельзя применить к указанному типу, так как он содержит описатель `auto`.

## <a name="example"></a>Пример

В следующем примере выдается C3541.

```cpp
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
