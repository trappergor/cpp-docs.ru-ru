---
title: Ошибка компилятора C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f9746ecb41e873fb1d929a939c78f1817dc0e2f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220279"
---
# <a name="compiler-error-c2663"></a>Ошибка компилятора C2663

"функция": числовые перегрузки не имеют допустимых преобразований для указателя "this"

Компилятору не удалось преобразовать **`this`** в ни одну из перегруженных версий функции члена.

Эта ошибка может быть вызвана вызовом функции, не являющейся **`const`** членом, для **`const`** объекта.  Возможные решения:

1. Удалите **`const`** из объявления объекта.

1. Добавьте **`const`** в одну из перегрузок функции члена.

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
