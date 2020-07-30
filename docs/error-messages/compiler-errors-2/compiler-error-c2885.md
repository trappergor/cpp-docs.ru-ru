---
title: Ошибка компилятора C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 9b6b7bb54d5dce48dc6fce517eb0c909b0284da2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233448"
---
# <a name="compiler-error-c2885"></a>Ошибка компилятора C2885

"класс:: идентификатор": не является допустимым объявлением using в области видимости, отличной от класса

Недопустимое [Использование объявления using](../../cpp/using-declaration.md) .

## <a name="example"></a>Пример

Эта ошибка может возникать в результате действий по согласованности компилятора, выполненных для Visual Studio 2005: объявление вложенного типа больше не является допустимым **`using`** . необходимо явно определить каждую ссылку на вложенный тип, разместить тип в пространстве имен или создать определение типа.

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

## <a name="example"></a>Пример

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
