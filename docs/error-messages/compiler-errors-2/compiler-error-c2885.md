---
title: Ошибка компилятора C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: ff5e770052301e95f694d3712f95b82732c2faba
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447696"
---
# <a name="compiler-error-c2885"></a>Ошибка компилятора C2885

«класс::идентификатор»: не недопустимое объявление в область вне класса

Вы использовали [с помощью](../../cpp/using-declaration.md) объявление неправильно.

## <a name="example"></a>Пример

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio 2005: он больше не может быть `using` объявление вложенного типа; необходимо явно указывать каждой ссылки, внесенные во вложенный тип, поместить тип в n amespace, текущей.

Следующий пример приводит к возникновению ошибки C2885.

```
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

Если вы используете `using` ключевое слово с членом класса C++, необходимо определить этот член внутри другого класса (производном классе).

Следующий пример приводит к возникновению ошибки C2885.

```
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