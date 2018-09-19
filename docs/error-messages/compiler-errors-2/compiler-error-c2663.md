---
title: Ошибка компилятора C2663 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fed35dcce056eb3d2a660c154e94b8058563dba7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083695"
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