---
title: Ошибка компилятора C2108 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2108
dev_langs:
- C++
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6b3f1ce5017a87ba682fcf6463fef5a30307460
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082317"
---
# <a name="compiler-error-c2108"></a>Ошибка компилятора C2108

Индекс имеет нецелый целочисленный тип

Индекс массива является нецелочисленное.

## <a name="example"></a>Пример

C2108 может произойти, если вы неправильно используете `this` указатель типа значения для доступа к индексатору по умолчанию этого типа. Дополнительные сведения см. в разделе [семантики этого указатель](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Следующий пример приводит к возникновению ошибки C2108.

```
// C2108.cpp
// compile with: /clr
using namespace System;

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      Console::WriteLine("{0}", this[3.3]);   // C2108
      Console::WriteLine("{0}", this->default[3.3]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```