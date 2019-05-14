---
title: Ошибка компилятора C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 901e9b791616c5684b352c1fda7687f67b895d9c
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447374"
---
# <a name="compiler-error-c2027"></a>Ошибка компилятора C2027

Использование неопределенного типа «тип»

Тип не может использоваться, пока он определен. Чтобы устранить эту ошибку, убедитесь, что перед ее использованием полностью определен тип.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2027.

```
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

Это можно объявить указатель на объявленный, но неопределенный тип. Но C++ ссылка на неопределенный тип не разрешается.

Следующий пример приводит к возникновению ошибки C2027.

```
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