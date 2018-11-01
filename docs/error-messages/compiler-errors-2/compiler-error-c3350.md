---
title: Ошибка компилятора C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: a19dbde6409afaae29e9110315c7c68fe9d43d62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547216"
---
# <a name="compiler-error-c3350"></a>Ошибка компилятора C3350

"делегат": для конструктора делегата требуется "число" аргументов

При создании экземпляра делегата следует передавать два аргумента: экземпляр типа, содержащего функцию-делегат, и саму функцию.

Следующий пример приводит к возникновению ошибки C3350:

```
// C3350.cpp
// compile with: /clr
delegate void SumDelegate();

public ref class X {
public:
   void F() {}
   static void F2() {}
};

int main() {
   X ^ MyX = gcnew X();
   SumDelegate ^ pSD = gcnew SumDelegate();   // C3350
   SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F);
   SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2);
}
```
