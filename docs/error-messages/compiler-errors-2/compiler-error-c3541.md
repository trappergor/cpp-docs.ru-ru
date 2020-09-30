---
title: Ошибка компилятора C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 2d6179657462325a30de0c4548becff4b4cf86c9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508066"
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

[Ключевое слово auto](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto (вывод типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[типа](../../extensions/typeid-cpp-component-extensions.md)
