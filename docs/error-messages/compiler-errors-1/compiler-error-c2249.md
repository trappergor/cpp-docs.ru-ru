---
title: Ошибка компилятора C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: f50cb27a239e794b87a15920a36e96529bd6a466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212804"
---
# <a name="compiler-error-c2249"></a>Ошибка компилятора C2249

"член": нет доступного пути к члену, объявленному в виртуальном базовом классе "класс"

`member`Класс наследуется от неоткрытого **`virtual`** базового класса или структуры.

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
