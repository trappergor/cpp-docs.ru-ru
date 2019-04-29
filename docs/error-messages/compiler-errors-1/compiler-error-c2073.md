---
title: Ошибка компилятора C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 2b45d512224ec32459e6da040a6abb0211278e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303324"
---
# <a name="compiler-error-c2073"></a>Ошибка компилятора C2073

«Идентификатор»: элементы частично инициализированного массива должны иметь конструктор по умолчанию

Слишком мало инициализаторы были указаны для массив определяемых пользователем типов или константы. Если инициализатор явные и его соответствующий конструктор для члена массива не указаны, необходимо указать конструктор по умолчанию.

Следующий пример приводит к возникновению ошибки C2073:

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```