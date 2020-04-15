---
title: 'Как: Объявить переопределить specifiers (КЗ / CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 9f3f6855f257d0af250b9bbdd2c0360b308ce775
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374448"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI)

[запечатанные,](../extensions/sealed-cpp-component-extensions.md) [абстрактные,](../extensions/abstract-cpp-component-extensions.md)и [переопределение](../extensions/override-cpp-component-extensions.md) доступны в компиляциях, которые не используют **/ ЗВ** или [/clr](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Стандартный язык ISO C-11 имеет идентификатор [переопределения](../cpp/override-specifier.md) и [окончательный](../cpp/final-specifier.md) идентификатор, и оба поддерживаются в Visual Studio Use, `final` а не `sealed` в коде, который должен быть скомпилирован как родной только.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Ниже приводится `sealed` следующий пример, который действителен в родных компиляциях.

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

Следующий пример `override` показывает, что это действительно в родной компиляции.

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

Этот пример `abstract` показывает, что это действительно в родных компиляциях.

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
