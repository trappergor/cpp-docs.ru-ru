---
title: Ошибка компилятора C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: 4897512f6bd27465b7281d7a27757918128202d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489938"
---
# <a name="compiler-error-c2694"></a>Ошибка компилятора C2694

«override»: переопределяющая виртуальная функция обладает менее ограниченной спецификацией исключений, чем базовый класс функции виртуального члена «base»

Была переопределена виртуальная функция, но в разделе [/Za](../../build/reference/za-ze-disable-language-extensions.md), переопределение функции было менее строгий [спецификация исключений](../../cpp/exception-specifications-throw-cpp.md).

Следующий пример приводит к возникновению ошибки C2694:

```
// C2694.cpp
// compile with: /Za /c
class MyBase {
public:
   virtual void f(void) throw(int) {
   }
};

class Derived : public MyBase {
public:
   void f(void) throw(...) {}   // C2694
   void f2(void) throw(int) {}   // OK
};
```