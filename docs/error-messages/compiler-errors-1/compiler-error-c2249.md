---
title: Ошибка компилятора C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: ac396fe5fa3505311f5a45ebb49dae283e35248c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741422"
---
# <a name="compiler-error-c2249"></a>Ошибка компилятора C2249

"член": нет доступного пути к члену, объявленному в виртуальном базовом классе "класс"

`member`Класс наследуется от неоткрытого **`virtual`** базового класса или структуры.

## <a name="examples"></a>Примеры

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

C2249 также может возникать при попытке назначить поток из стандартной библиотеки C++ другому потоку.  Следующий пример приводит к возникновению ошибки C2249.

```cpp
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```
