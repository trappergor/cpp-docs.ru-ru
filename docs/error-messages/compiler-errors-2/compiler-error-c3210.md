---
title: Ошибка компилятора C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 513f08d4dddc37d36a240ee0d72b24383f951cdf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755126"
---
# <a name="compiler-error-c3210"></a>Ошибка компилятора C3210

"тип": объявление доступа может применяться только к члену базового класса

[Объявление using](../../cpp/using-declaration.md) указано неверно.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3210.

```cpp
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```
