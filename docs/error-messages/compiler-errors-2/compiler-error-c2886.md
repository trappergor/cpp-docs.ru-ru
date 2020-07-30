---
title: Ошибка компилятора C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 3e445b52c2a0abbfca198c4cb0f4108dd5ba5ffb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233435"
---
# <a name="compiler-error-c2886"></a>Ошибка компилятора C2886

"класс:: идентификатор": символ не может использоваться в объявлении с помощью-объявлением члена

В **`using`** объявлении используется символ, например имя пространства имен. **`using`** Объявление предназначено для объявления членов базового класса.

Следующий пример приводит к возникновению ошибки C2886:

```cpp
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```
