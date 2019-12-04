---
title: Ошибка компилятора C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: 680268948f8642b02768bd4b3092666982e14eb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759312"
---
# <a name="compiler-error-c2597"></a>Ошибка компилятора C2597

недопустимая ссылка на нестатический член identifier

Возможные причины.

1. Нестатический член используется в статической функции-члене. Для доступа к нестатическому члену необходимо передать или создать локальный экземпляр класса и использовать оператор доступа к члену (`.` или `->`).

1. Указанный идентификатор не является членом класса, структуры или объединения. Проверьте написание идентификатора.

1. Оператор доступа к члену ссылается на функцию, не являющуюся членом.

1. В следующем примере показано возникновение ошибки C2597 и приводятся сведения по ее устранению.

```cpp
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```
