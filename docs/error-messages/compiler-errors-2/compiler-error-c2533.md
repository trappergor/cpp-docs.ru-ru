---
title: Ошибка компилятора C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 6c598c2c5b3ac6d88fb843534cae240c65a2d322
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207918"
---
# <a name="compiler-error-c2533"></a>Ошибка компилятора C2533

identifier: конструкторы не разрешены для типа возвращаемого значения

Конструктор не может иметь тип возвращаемого значения (даже **`void`** тип возвращаемого значения).

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
