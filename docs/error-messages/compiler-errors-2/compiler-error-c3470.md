---
title: Ошибка компилятора C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: 7d6c8627fe0904dd2fe81dd805d8f87bbebf29c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504463"
---
# <a name="compiler-error-c3470"></a>Ошибка компилятора C3470

"тип": класс не может одновременно иметь и индексатор (индексированное свойство по умолчанию), и operator[]

Тип не может задавать и индексатор по умолчанию, и оператор[].

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3470:

```
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