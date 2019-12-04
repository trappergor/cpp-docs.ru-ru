---
title: Ошибка компилятора C2107
ms.date: 11/04/2016
f1_keywords:
- C2107
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
ms.openlocfilehash: e492f58717a8356da54f7f26bd0d5db905f858a0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745880"
---
# <a name="compiler-error-c2107"></a>Ошибка компилятора C2107

Недопустимый индекс, косвенное обращение запрещено

Индекс применяется к выражению, которое не возвращает указатель.

## <a name="example"></a>Пример

C2107 может возникнуть при неправильном использовании `this` указателя типа значения для доступа к индексатору по умолчанию для типа. Дополнительные сведения см. [в разделе Семантика этого указателя](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Следующий пример приводит к возникновению ошибки C2107.

```cpp
// C2107.cpp
// compile with: /clr
using namespace System;

value struct B {
   property String ^ default[String ^] {
      String ^ get(String ^ data) {
         return "abc";
      }
   }
   void Test() {
      Console::WriteLine("{0}", this["aa"]);   // C2107
      Console::WriteLine("{0}", this->default["aa"]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```
