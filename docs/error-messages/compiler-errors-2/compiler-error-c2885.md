---
title: Ошибка компилятора C2885 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf47d830980b9fb93481f575e3e3a806ce8bbf68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035699"
---
# <a name="compiler-error-c2885"></a>Ошибка компилятора C2885

«класс::идентификатор»: не недопустимое объявление в область вне класса

Вы использовали [с помощью](../../cpp/using-declaration.md) объявление неправильно.

## <a name="example"></a>Пример

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: он больше не может быть `using` объявление вложенного типа; следует явно квалифицировать каждой ссылки, внесенные во вложенный тип, поместить тип в имени пробел, или создайте typedef.

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