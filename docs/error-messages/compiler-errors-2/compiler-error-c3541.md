---
title: Ошибка компилятора C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 03361fa3e8d4ecb9647d354dd402a9f2b0865eb6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037689"
---
# <a name="compiler-error-c3541"></a>Ошибка компилятора C3541

«Тип»: typeid нельзя применять к типу, содержащему «auto»

[Typeid](../../extensions/typeid-cpp-component-extensions.md) оператор не может применяться к указанному типу, так как она содержит `auto` спецификатор.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3541.

```
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
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)