---
title: Ошибка компилятора C2698 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7ca3e7568640aabd2b7960d97ea94a11a1d5d59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118925"
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