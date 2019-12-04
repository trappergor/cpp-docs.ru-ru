---
title: Ошибка компилятора C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: 24db84c9205173f098e493c4ea6393fb96592276
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758896"
---
# <a name="compiler-error-c2249"></a>Ошибка компилятора C2249

"член": нет доступного пути к члену, объявленному в виртуальном базовом классе "класс"

`member` наследуется от общедоступного `virtual` базового класса или структуры.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2249.

```cpp
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

## <a name="example"></a>Пример

C2249 также может возникать при попытке назначить поток из C++ стандартной библиотеки в другой поток.  Следующий пример приводит к возникновению ошибки C2249.

```cpp
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```
