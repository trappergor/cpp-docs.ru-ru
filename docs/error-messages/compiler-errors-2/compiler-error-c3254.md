---
title: Ошибка компилятора C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7e051c6c44d3b85f6f3faaf5380ecf54cba5d73c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470672"
---
# <a name="compiler-error-c3254"></a>Ошибка компилятора C3254

«явное переопределение»: класс содержит явное переопределение «override», но не является производным от интерфейса, который содержит объявление функции

Когда вы [явно переопределить](../../cpp/explicit-overrides-cpp.md) метода, класса, который содержит переопределенный метод должен быть производным, прямо или косвенно, из типа, содержащего функцию переопределяемой.

Следующий пример приводит к возникновению ошибки C3254:

```
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```