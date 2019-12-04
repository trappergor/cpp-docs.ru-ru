---
title: Ошибка компилятора C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f07b63202d8f171dfb69f4bb294b392152b9290b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756036"
---
# <a name="compiler-error-c2663"></a>Ошибка компилятора C2663

"функция": числовые перегрузки не имеют допустимых преобразований для указателя "this"

Компилятору не удалось преобразовать `this` в любую из перегруженных версий функции – члена.

Эта ошибка может быть вызвана вызовом функции-члена, не являющейся`const`, в объекте `const`.  Возможные решения:

1. Удалите `const` из объявления объекта.

1. Добавьте `const` в одну из перегрузок функции члена.

Следующий пример приводит к возникновению ошибки C2663:

```cpp
// C2663.cpp
struct C {
   void f() volatile {}
   void f() {}
};

struct D {
   void f() volatile;
   void f() const {}
};

const C *pcc;
const D *pcd;

int main() {
   pcc->f();    // C2663
   pcd->f();    // OK
}
```
