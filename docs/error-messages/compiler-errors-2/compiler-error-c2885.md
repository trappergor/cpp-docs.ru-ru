---
title: Ошибка компилятора C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 1953cb8fb9f80c5c1f967e10583c2b7303075f59
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742675"
---
# <a name="compiler-error-c2885"></a>Ошибка компилятора C2885

"класс:: идентификатор": не является допустимым объявлением using в области видимости, отличной от класса

Недопустимое [Использование объявления using](../../cpp/using-declaration.md) .

Эта ошибка может возникать в результате действий по согласованности компилятора, выполненных для Visual Studio 2005: объявление вложенного типа больше не является допустимым **`using`** . необходимо явно определить каждую ссылку на вложенный тип, разместить тип в пространстве имен или создать определение типа.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2885.

```cpp
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

При использовании **`using`** ключевого слова с членом класса C++ требует определения этого члена внутри другого класса (производного класса).

Следующий пример приводит к возникновению ошибки C2885.

```cpp
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```
