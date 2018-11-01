---
title: Ошибка компилятора C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 8238dcec821256dad8101cd7ad59b2d85882c218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622876"
---
# <a name="compiler-error-c3149"></a>Ошибка компилятора C3149

«Тип»: нельзя использовать этот тип без верхнего уровня «char»

Объявление не был указан правильно.

Например может определения типа CLR в глобальной области видимости и пытается создать переменную типа как часть определения. Так как глобальные переменные типов CLR не допускаются, компилятор создаст C3149.

Чтобы устранить эту ошибку, объявите переменные типов CLR в определении функции или типа.

Следующий пример приводит к возникновению ошибки C3149:

```
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Следующий пример приводит к возникновению ошибки C3149:

```
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
