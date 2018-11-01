---
title: Ошибка компилятора C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 2fa7450f03505501c2c4a45023dbb6a86937bb9c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586684"
---
# <a name="compiler-error-c2886"></a>Ошибка компилятора C2886

«класс::идентификатор»: символ не может использоваться в с помощью объявление члена

Объект `using` объявлении используется символ, например имя пространства имен. Объект `using` объявления предназначены для объявления членов базового класса.

Следующий пример приводит к возникновению ошибки C2886:

```
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