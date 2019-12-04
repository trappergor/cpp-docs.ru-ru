---
title: Ошибка компилятора C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: aa3e97d576e994878ab5b080363c4c09b79f42ed
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756790"
---
# <a name="compiler-error-c2553"></a>Ошибка компилятора C2553

"base_function": возвращаемый тип переопределяемой виртуальной функции отличается от "override_function"

Функция в производном классе попыталась переопределить виртуальную функцию в базовом классе, но функция производного класса не имеет того же типа возвращаемого значения, что и функция базового класса.  Сигнатура функции переопределения должна соответствовать сигнатуре переопределяемой функции.

Следующий пример приводит к возникновению ошибки C2553:

```cpp
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```
