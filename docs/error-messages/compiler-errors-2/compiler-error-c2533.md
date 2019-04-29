---
title: Ошибка компилятора C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 00cb13d1999b00dfcaa5a2bc7bfb3b8eb16af5f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386984"
---
# <a name="compiler-error-c2533"></a>Ошибка компилятора C2533

identifier: конструкторы не разрешены для типа возвращаемого значения

Конструктор класса не может иметь возвращаемый тип (даже тип `void`).

Типичной причиной возникновения этой ошибки является отсутствие точки с запятой между концом определения класса и первой реализацией конструктора. Компилятор считает класс определением типа возвращаемого значения для функции конструктора класса и вызывает ошибку C2533.

В следующем примере показано возникновение ошибки C2533 и приводятся сведения по ее устранению.

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```