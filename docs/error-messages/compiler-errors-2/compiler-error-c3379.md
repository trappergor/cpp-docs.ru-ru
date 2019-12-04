---
title: Ошибка компилятора C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 9d99214f3ad7e7db1edc215d94c98e9cf9ec4ca2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742903"
---
# <a name="compiler-error-c3379"></a>Ошибка компилятора C3379

"класс": вложенный класс не может иметь спецификатор доступа к сборке в рамках своего объявления

При применении к управляемому типу, например классу или структуре, ключевые слова [Public](../../cpp/public-cpp.md) и [Private](../../cpp/private-cpp.md) указывают, будет ли класс предоставлен через метаданные сборки. `public` или `private` нельзя применить к вложенному классу, который будет наследовать доступ к сборке включающего класса.

При использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)ключевые слова `ref` и `value` указывают, что класс является управляемым (см. [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Следующий пример приводит к возникновению ошибки C3379:

```cpp
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
