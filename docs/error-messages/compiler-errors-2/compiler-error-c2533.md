---
title: Ошибка компилятора C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: b111448e7e9d8260a5101d05996a670013936894
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746413"
---
# <a name="compiler-error-c2533"></a>Ошибка компилятора C2533

identifier: конструкторы не разрешены для типа возвращаемого значения

Конструктор класса не может иметь возвращаемый тип (даже тип `void`).

Типичной причиной возникновения этой ошибки является отсутствие точки с запятой между концом определения класса и первой реализацией конструктора. Компилятор считает класс определением типа возвращаемого значения для функции конструктора класса и вызывает ошибку C2533.

В следующем примере показано возникновение ошибки C2533 и приводятся сведения по ее устранению.

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
