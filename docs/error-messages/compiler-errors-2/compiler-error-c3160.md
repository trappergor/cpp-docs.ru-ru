---
title: Ошибка компилятора C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 96fd97aa5021b7e1bc5226162f9c54ff4d6211b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649752"
---
# <a name="compiler-error-c3160"></a>Ошибка компилятора C3160

pointer: данные-член управляемого класса или класса WinRT не могут иметь этот тип

Внутренние указатели сборки мусора могут указывать на внутреннюю часть управляемого класса или класса WinRT. Так как они выполняются медленнее, чем указатели на весь объект, и требуют специальной обработки сборщиком мусора, внутренние управляемые указатели нельзя объявлять как члены класса.

Следующий пример приводит к возникновению ошибки C3160:

```
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
