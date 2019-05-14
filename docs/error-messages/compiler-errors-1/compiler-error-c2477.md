---
title: Ошибка компилятора C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 73d8daa9576e4edc29958918c107e9edf18cc579
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447968"
---
# <a name="compiler-error-c2477"></a>Ошибка компилятора C2477

«член»: статические данные-член не могут быть инициализированы в производном классе

Статические данные-член шаблона класса был инициализирован неправильно. Это критическое изменение в версиях Microsoft C++ компилятора до Visual Studio .NET 2003, чтобы соответствовать ISO C++ standard.

Следующий пример приводит к возникновению ошибки C2477:

```
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```