---
title: Ошибка компилятора C2977
ms.date: 11/04/2016
f1_keywords:
- C2977
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
ms.openlocfilehash: eaf314276b2fdf536c1d11c0e0752a6de396b5a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751681"
---
# <a name="compiler-error-c2977"></a>Ошибка компилятора C2977

"идентификатор": слишком много аргументов типа

Универсальный класс или шаблон имеет слишком много фактических аргументов. Проверьте объявление универсального класса или шаблона, чтобы определить правильное число параметров.

Следующий пример приводит к возникновению ошибки C2977:

```cpp
// C2977.cpp
// compile with: /c
template<class T, int i>
class MyClass {};

template MyClass< int , 1, 1 >;   // C2977
template MyClass< int , 1 >;   // OK
```

Ошибка C2977 также может возникнуть при использовании универсальных шаблонов.

```cpp
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
