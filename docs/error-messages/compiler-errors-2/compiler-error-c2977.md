---
title: Ошибка компилятора C2977
ms.date: 11/04/2016
f1_keywords:
- C2977
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
ms.openlocfilehash: c9f2971c60b2d1bbc703696467040c3b1d2e2756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395343"
---
# <a name="compiler-error-c2977"></a>Ошибка компилятора C2977

"идентификатор": слишком много аргументов типа

Универсальный класс или шаблон имеет слишком много фактических аргументов. Проверьте объявление универсального класса или шаблона, чтобы определить правильное число параметров.

Следующий пример приводит к возникновению ошибки C2977:

```
// C2977.cpp
// compile with: /c
template<class T, int i>
class MyClass {};

template MyClass< int , 1, 1 >;   // C2977
template MyClass< int , 1 >;   // OK
```

Ошибка C2977 также может возникнуть при использовании универсальных шаблонов.

```
// C2977b.cpp
// compile with: /clr
// C2977 expected
generic <class T, class U>
void f(){}

generic <class T>
ref struct GC1 {};

int main() {
   // Delete the following 2 lines to resolve.
   GC1<int, char> ^ pgc1;
   f<int,int,int>();

   // OK
   GC1<int> ^ pgc1;
   f<int, int>();
}
```