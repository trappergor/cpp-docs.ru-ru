---
title: Ошибка компилятора C3736
ms.date: 11/04/2016
f1_keywords:
- C3736
helpviewer_keywords:
- C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
ms.openlocfilehash: 9c4626164fe8fe3fb932fba3ae8e87c774f5aeec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752851"
---
# <a name="compiler-error-c3736"></a>Ошибка компилятора C3736

"Event": должен быть методом или, в случае с управляемыми событиями, необязательный элемент данных

События native и COM должны быть методами. События .NET также могут быть членами данных.

Следующий пример приводит к возникновению ошибки C3736:

```cpp
// C3736.cpp
struct A {
   __event int e();
};

struct B {
   int f;   // C3736
   // The following line resolves the error.
   // int f();
   B(A* a) {
      __hook(&A::e, a, &B::f);
   }
};

int main() {
}
```
