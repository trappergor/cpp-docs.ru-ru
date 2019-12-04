---
title: Ошибка компилятора C2647
ms.date: 11/04/2016
f1_keywords:
- C2647
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
ms.openlocfilehash: 9553c85efeedb4d3eee4bd40f9e3b86707fd7eb1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758389"
---
# <a name="compiler-error-c2647"></a>Ошибка компилятора C2647

"оператор": невозможно отменять ссылку на "тип1" для "тип2"

Левый операнд оператора указателя на член (`->*` или `.*`) не может быть неявно преобразован в тип, связанный с оператором right.

Следующий пример приводит к возникновению ошибки C2647:

```cpp
// C2647.cpp
class C {};
class D {};

int main() {
   D d, *pd;
   C c, *pc = 0;
   int C::*pmc = 0;
   pd->*pmc = 0;   // C2647
   d.*pmc = 0;   // C2647

   // OK
   pc->*pmc = 0;
   c.*pmc = 0;
}
```
