---
title: Ошибка компилятора C3637
ms.date: 11/04/2016
f1_keywords:
- C3637
helpviewer_keywords:
- C3637
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
ms.openlocfilehash: c79a4113e20e3798877ccda8f1392b276dee19fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574464"
---
# <a name="compiler-error-c3637"></a>Ошибка компилятора C3637

«функция»: определение дружественной функции не может быть специализацией типом функции

Дружественная функция было неправильно задано для шаблона или универсального.

Следующий пример приводит к возникновению ошибки C3637:

```
// C3637.cpp
template <class T>
void f();

struct S {
   friend void f<int>() {}   // C3637
};
```

Возможное решение

```
// C3637b.cpp
// compile with: /c
template <class T>
void f();

struct S {
   friend void f() {}
};
```

C3637 также может возникнуть при использовании универсальных шаблонов:

```
// C3637c.cpp
// compile with: /clr

generic <class T>
void gf();

struct S {
   friend void gf<int>() {}   // C3637
};
```

Возможное решение

```
// C3637d.cpp
// compile with: /clr /c
generic <class T>
void gf();

struct S {
   friend void gf() {}
};
```