---
title: Инструкции. объявление описателей переопределения (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 92bdc41cf9ebe2389f2d22dab211029899283266
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414598"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI)

[запечатанные](../extensions/sealed-cpp-component-extensions.md), [абстрактные](../extensions/abstract-cpp-component-extensions.md)и [переопределения](../extensions/override-cpp-component-extensions.md) доступны в компиляциях, которые не используют **/ZW** или [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Стандартный язык ISO C++ 11 имеет идентификатор [переопределения](../cpp/override-specifier.md) и [конечный](../cpp/final-specifier.md) идентификатор, и обе эти версии поддерживаются в Visual Studio `final` вместо **`sealed`** в коде, который должен компилироваться только как машинный код.

## <a name="example-sealed-is-valid"></a>Пример: Sealed является допустимым

### <a name="description"></a>Описание

В следующем примере показано, что **`sealed`** допустимо в компиляциях в собственном режиме.

### <a name="code"></a>Код

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example-override-is-valid"></a>Пример: переопределение допустимо

### <a name="description"></a>Описание

В следующем примере показано, что `override` допустимо в компиляциях в машинном код.

### <a name="code"></a>Код

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example-abstract-is-valid"></a>Пример: abstract является допустимым

### <a name="description"></a>Описание

В этом примере показано, что **`abstract`** допустимо в компиляциях в машинном код.

### <a name="code"></a>Код

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>См. также

[Спецификаторы переопределения](../extensions/override-specifiers-cpp-component-extensions.md)
