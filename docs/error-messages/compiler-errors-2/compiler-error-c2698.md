---
title: Ошибка компилятора C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: f643b7d8c035b4d1d7d8806feb5b121cf76d7796
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367581"
---
# <a name="compiler-error-c2698"></a>Ошибка компилятора C2698

объявление using для "объявления 1" не могут сосуществовать с существующей объявление using для "объявления 2"

При наличии [объявление using](../../cpp/using-declaration.md) для члена данных, любое использование не допускается объявление в той же области, которая использует то же имя, как только функции могут быть перегружены.

Следующий пример приводит к возникновению ошибки C2698:

```
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```