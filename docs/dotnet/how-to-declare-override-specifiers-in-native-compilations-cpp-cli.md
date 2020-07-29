---
title: Инструкции. объявление описателей переопределения (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: c5ed413f403fb12f116633c0e39f9e7b32b2e9f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221332"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI)

[запечатанные](../extensions/sealed-cpp-component-extensions.md), [абстрактные](../extensions/abstract-cpp-component-extensions.md)и [переопределения](../extensions/override-cpp-component-extensions.md) доступны в компиляциях, которые не используют **/ZW** или [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Стандартный язык ISO C++ 11 имеет идентификатор [переопределения](../cpp/override-specifier.md) и [конечный](../cpp/final-specifier.md) идентификатор, и обе эти версии поддерживаются в Visual Studio `final` вместо **`sealed`** в коде, который должен компилироваться только как машинный код.

## <a name="example"></a>Пример

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

## <a name="example"></a>Пример

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

## <a name="example"></a>Пример

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

## <a name="see-also"></a>См. также раздел

[Спецификаторы переопределения](../extensions/override-specifiers-cpp-component-extensions.md)
