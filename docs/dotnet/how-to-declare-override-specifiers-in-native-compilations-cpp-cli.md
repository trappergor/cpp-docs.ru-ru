---
title: Практическое руководство. Объявление спецификаторов переопределения (C++выполняет)
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: db74ef226242ec8f4f70f2769fbc8ba102a808c8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777185"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++выполняет)

[Запечатанный](../extensions/sealed-cpp-component-extensions.md), [абстрактный](../extensions/abstract-cpp-component-extensions.md), и [переопределить](../extensions/override-cpp-component-extensions.md) доступны в компиляциях, не использующих **/ZW** или [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
>  ISO C ++ 11 Standard язык имеет [переопределить](../cpp/override-specifier.md) идентификатор и [окончательный](../cpp/final-specifier.md) идентификатор и оба поддерживаются в Visual Studio используйте `final` вместо `sealed` в коде, который предназначен для скомпилировать как только машинный код.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показано, что `sealed` является допустимым в компиляции в машинный код.

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

В следующем примере показано, что `override` является допустимым в компиляции в машинный код.

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

В этом примере показано, что `abstract` является допустимым в компиляции в машинный код.

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
