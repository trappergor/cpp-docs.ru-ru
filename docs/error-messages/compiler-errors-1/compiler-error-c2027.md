---
title: Ошибка компилятора C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 62cf208d9d0025afba06d32a15b9a1e50777c473
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751005"
---
# <a name="compiler-error-c2027"></a>Ошибка компилятора C2027

Использование неопределенного типа "тип"

Тип нельзя использовать, пока не будет определен. Чтобы устранить эту ошибку, убедитесь, что тип определен полностью, прежде чем ссылаться на него.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2027.

```cpp
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>Пример

Можно объявить указатель на объявленный, но неопределенный тип. Но C++ не допускает ссылку на неопределенный тип.

Следующий пример приводит к возникновению ошибки C2027.

```cpp
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```
