---
title: Ошибка компилятора C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: 093efbf0c329967983c1808ee46011425745515f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595811"
---
# <a name="compiler-error-c2877"></a>Ошибка компилятора C2877

«символ» не будет доступна из «class»

Все члены, унаследованные от базового класса должны быть доступны в производном классе.

Следующий пример приводит к возникновению ошибки C2877:

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```