---
title: Ошибка компилятора C3736
ms.date: 11/04/2016
f1_keywords:
- C3736
helpviewer_keywords:
- C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
ms.openlocfilehash: e31d68a13ebd9c5267fd285d43ebc66ae8b53182
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584201"
---
# <a name="compiler-error-c3736"></a>Ошибка компилятора C3736

«событие»: должен быть методом или, в случае управляемых событий, при необходимости элемент данных

Машинный код и COM-событий должны быть методами. События .NET также могут быть данные-члены.

Следующий пример приводит к возникновению ошибки C3736:

```
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