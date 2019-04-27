---
title: Ошибка компилятора C2974
ms.date: 11/04/2016
f1_keywords:
- C2974
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
ms.openlocfilehash: 2fa0fae07435f3ab63398b7b3f02f9c662e7b436
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256574"
---
# <a name="compiler-error-c2974"></a>Ошибка компилятора C2974

Недопустимый тип аргумента «number» требуется тип

Аргумент универсального класса или шаблона не соответствует объявлению универсального класса или шаблона. Тип должен появиться в угловых скобках. Проверьте определение универсального класса или шаблона, чтобы найти правильные типы.

Следующий пример приводит к возникновению ошибки C2974:

```
// C2974.cpp
// C2974 expected
template <class T>
struct TC {};

template <typename T>
void tf(T){}

int main() {
   // Delete the following 2 lines to resolve
   TC<1>* tc;
   tf<"abc">("abc");

   TC<int>* tc;
   tf<const char *>("abc");
}
```

C2974 также может возникнуть при использовании универсальных шаблонов:

```
// C2974b.cpp
// compile with: /clr
// C2974 expected
using namespace System;
generic <class T>
ref struct GCtype {};

generic <typename T>
void gf(T){}

int main() {
   // Delete the following 2 lines to resolve
   GCtype<"a">^ gc;
   gf<"a">("abc");

   // OK
   GCtype<int>^ gc;
   gf<String ^>("abc");
}
```