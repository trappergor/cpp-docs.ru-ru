---
title: Ошибка компилятора C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b7bdd10ebd70eb61746690958532854dd98c6429
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641198"
---
# <a name="compiler-error-c2597"></a>Ошибка компилятора C2597

недопустимая ссылка на нестатический член identifier

Возможные причины:

1. Нестатический член используется в статической функции-члене. Для доступа к нестатическому члену необходимо передать или создать локальный экземпляр класса и использовать оператор доступа к члену (`.` или `->`).

1. Указанный идентификатор не является членом класса, структуры или объединения. Проверьте написание идентификатора.

1. Оператор доступа к члену ссылается на функцию, не являющуюся членом.

1. В следующем примере показано возникновение ошибки C2597 и приводятся сведения по ее устранению.

```
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