---
title: Ошибка компилятора C2597 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9f8deb325ae54393518698263f3ca93ca88ca48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114453"
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