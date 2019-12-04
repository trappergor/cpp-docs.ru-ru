---
title: Ошибка компилятора C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d0e283c7cd6116655a56f8df67ab4eecf9923b68
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760945"
---
# <a name="compiler-error-c2884"></a>Ошибка компилятора C2884

"имя": появилось при конфликте объявления using с локальной функцией "функция"

Вы попытались определить функцию несколько раз. Первое определение — это локальное определение. Второй — из пространства имен с объявлением `using`.

Следующий пример приводит к возникновению ошибки C2884:

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
