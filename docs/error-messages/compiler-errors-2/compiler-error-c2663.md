---
title: Ошибка компилятора C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: d74326e49edd980896276e2c6e67526d8d769cb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360298"
---
# <a name="compiler-error-c2663"></a>Ошибка компилятора C2663

«функция»: перегрузок не имеют действительных преобразований для указатель «this»

Компилятору не удалось преобразовать `this` на любой из перегруженных версий функции-члена.

Эта ошибка может быть вызвана путем вызова отличный от`const` функции-члена `const` объекта.  Возможные решения:

1. Удалить `const` из объявления объекта.

1. Добавить `const` к одной из перегрузок функции-члена.

Следующий пример приводит к возникновению ошибки C2663:

```
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