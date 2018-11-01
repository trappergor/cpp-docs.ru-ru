---
title: Ошибка компилятора C3421
ms.date: 11/04/2016
f1_keywords:
- C3421
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
ms.openlocfilehash: 399224a3d091a26066a03df0c77511997ae2403c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448910"
---
# <a name="compiler-error-c3421"></a>Ошибка компилятора C3421

"тип": невозможно вызвать метод завершения для данного класса, поскольку он либо недоступен, либо не существует

Метод завершения является неявно закрытым, поэтому его нельзя вызвать за пределами включающего типа.

Дополнительные сведения см. в разделе [деструкторы и методы завершения в разделе: определение и использование классов и структур (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3421:

```
// C3421.cpp
// compile with: /clr
ref class A {};

ref class B {
   !B() {}

public:
   ~B() {}
};

int main() {
   A a;
   a.!A();   // C3421

   B b;
   b.!B();   // C3421
}
```