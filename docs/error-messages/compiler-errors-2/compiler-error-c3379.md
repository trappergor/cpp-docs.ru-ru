---
title: Ошибка компилятора C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 5bf4e2e42b4534d47a2a7d3c9a838c404a99ba68
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769995"
---
# <a name="compiler-error-c3379"></a>Ошибка компилятора C3379

«класс»: вложенный класс не может иметь спецификатор уровня доступа сборки как часть объявления

При применении к управляемому типу, например класса или структуры, [открытый](../../cpp/public-cpp.md) и [частного](../../cpp/private-cpp.md) означают возможность предоставления класса посредством метаданных сборки. `public` или `private` не может применяться к вложенному классу, доступ к сборке, включающего класса.

При использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` и `value` означают, что управляемый класс (см. в разделе [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Следующий пример приводит к возникновению ошибки C3379:

```
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
