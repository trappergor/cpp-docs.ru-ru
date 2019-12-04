---
title: Ошибка компилятора C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: cb6b1043d976cfeb8cb92c8780c5b84ea9700b8b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760958"
---
# <a name="compiler-error-c2883"></a>Ошибка компилятора C2883

"имя": объявление функции конфликтует с "идентификатором", представленным с помощью объявления using

Вы попытались определить функцию несколько раз. Первое определение было создано из пространства имен с объявлением `using`. Второй является локальным определением.

Следующий пример приводит к возникновению ошибки C2883:

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
