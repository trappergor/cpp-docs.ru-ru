---
title: Ошибка компилятора C2635
ms.date: 11/04/2016
f1_keywords:
- C2635
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
ms.openlocfilehash: 0c31bcc4062aec1d939c801f9b5ee420f2f4fcb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468124"
---
# <a name="compiler-error-c2635"></a>Ошибка компилятора C2635

не удается преобразовать «идентификатор1 *» в "идентификатор2\*"; предполагается преобразование из виртуального базового класса

Процесс преобразования требует приведения к типу из `virtual` базового класса в производном классе, что не допускается.

Следующий пример приводит к возникновению ошибки C2635:

```
// C2635.cpp
class B {};
class D : virtual public B {};
class E : public B {};

int main() {
   B b;
   D d;
   E e;

   D * pD = &d;
   E * pE = &e;
   pD = (D*)&b;   // C2635
   pE = (E*)&b;   // OK
}
```