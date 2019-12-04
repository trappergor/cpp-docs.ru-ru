---
title: Ошибка компилятора C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: e9bda55c7a65eb5eec4e1f5104a779a817ad5c36
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760495"
---
# <a name="compiler-error-c3470"></a>Ошибка компилятора C3470

"тип": класс не может одновременно иметь и индексатор (индексированное свойство по умолчанию), и operator[]

Тип не может задавать и индексатор по умолчанию, и оператор[].

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3470:

```cpp
// C3470.cpp
// compile with: /clr
using namespace System;

ref class R {
public:
   property int default[int] {
      int get(int i) {
         return i+1;
      }
   }

   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470
};

int main() {
   R ^ r = gcnew R;
   // return r[9] + r["32"] - 42;
}
```
