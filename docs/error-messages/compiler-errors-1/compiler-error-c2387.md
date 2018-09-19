---
title: Ошибка компилятора C2387 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2387
dev_langs:
- C++
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a73f2964c7f87ba795ba680947664a0f37b9c303
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089623"
---
# <a name="compiler-error-c2387"></a>Ошибка компилятора C2387

«Тип»: неоднозначный базовый класс

Компилятору не удалось однозначно разрешить вызов функции, поскольку функция существует в более чем одного базового класса.

Чтобы устранить эту ошибку, удалите один из базовых классов из наследования или явным образом квалифицировать вызов функции.

Следующий пример приводит к возникновению ошибки C2387:

```
// C2387.cpp
namespace N1 {
   struct B {
      virtual void f() {
      }
   };
}

namespace N2 {
   struct B {
      virtual void f() {
      }
   };
}

struct D : N1::B, N2::B {
   virtual void f() {
      B::f();   // C2387
      // try the following line instead
      // N1::B::f();
   }
};

int main() {
   D aD;
   aD.f();
}
```