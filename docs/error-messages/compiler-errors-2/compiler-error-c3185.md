---
title: Ошибка компилятора C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: db448b462cd3a3f325c529e730e5c8f65e2b8f51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598814"
---
# <a name="compiler-error-c3185"></a>Ошибка компилятора C3185

typeid используется для управляемого типа или типа WinRT "type", вместо этого используйте operator

Невозможно применить [typeid](../../cpp/typeid-operator.md) оператор в управляемый "или" WinRT типа; используйте [typeid](../../windows/typeid-cpp-component-extensions.md) вместо этого.

В следующем примере показано возникновение ошибки C3185 и приводятся сведения по ее устранению.

```
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
