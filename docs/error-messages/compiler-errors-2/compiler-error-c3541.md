---
title: Ошибка компилятора C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 32926d0ef9343bad9ed73458e4d52d317b628109
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221046"
---
# <a name="compiler-error-c3541"></a>Ошибка компилятора C3541

"тип": typeid нельзя применять к типу, содержащему "Auto"

Оператор [typeid](../../extensions/typeid-cpp-component-extensions.md) не может применяться к указанному типу, так как он содержит **`auto`** спецификатор.

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

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc: Auto (вывод типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[типа](../../extensions/typeid-cpp-component-extensions.md)
