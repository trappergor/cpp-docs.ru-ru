---
title: Ошибка компилятора C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: a5b483f3aaa82e543d561cb7c550495069a19f7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519942"
---
# <a name="compiler-error-c3255"></a>Ошибка компилятора C3255

«Тип значения»: не удается динамически выделить этот объект типа значения в собственной куче

Экземпляры типа значения (см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)), содержащие управляемые члены могут быть созданы в стеке, но не в куче.

Следующий пример приводит к возникновению ошибки C3255:

```
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
