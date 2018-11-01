---
title: Ошибка компилятора C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 11cb2b83d958f0c59d05034a716a022f00b326ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658683"
---
# <a name="compiler-error-c2553"></a>Ошибка компилятора C2553

«базовая_функция»: переопределение виртуальной функции возвращают тип отличается от «переопределяющая_функция»

Функция в производном классе предпринята попытка переопределить виртуальную функцию в базовом классе, но функция производного класса не было совпадает с типом возвращаемого значения функции базового класса.  Подпись переопределяющей функции должна соответствовать сигнатуре функции переопределения.

Следующий пример приводит к возникновению ошибки C2553:

```
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