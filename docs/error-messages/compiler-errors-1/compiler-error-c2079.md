---
title: Ошибка компилятора C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: ea158d8dada013f6b90d0fbe1e7502665c1c24da
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757726"
---
# <a name="compiler-error-c2079"></a>Ошибка компилятора C2079

"идентификатор" использует неопределенный класс, структуру или объединение "имя"

Указанный идентификатор является неопределенным классом, структурой или объединением.

Эта ошибка может быть вызвана инициализацией анонимного объединения.

Следующий пример приводит к возникновению ошибки C2079:

```cpp
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Возможное решение

```cpp
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 также может возникать при попытке объявить объект в стеке типа, объявление прямого объявления которого находится только в области.

```cpp
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Возможное решение

```cpp
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```
