---
title: Ошибка компилятора C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: 472aabf00fecd000f274d97b5753ed8460ff867f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758870"
---
# <a name="compiler-error-c2250"></a>Ошибка компилятора C2250

"идентификатор": неоднозначное наследование "класс:: член"

Производный класс наследует больше одного переопределения виртуальной функции виртуального базового класса. Эти переопределения являются неоднозначными в производном классе.

При компиляции следующего примера возникнет ошибка C2286:

```cpp
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```
