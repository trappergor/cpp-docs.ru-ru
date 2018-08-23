---
title: Списки аргументов переменных (...) (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e58b7ea2d8db0c3d36ad36aaccbf23957c449a77
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590467"
---
# <a name="variable-argument-lists--ccli"></a>Списки аргументов переменных (...) (C++/CLI)

В этом примере показано, как можно использовать `...` синтаксис в Visual C++ для реализации функций с переменным числом аргументов.

> [!NOTE]
> В этом разделе относится к C + +/ CLI. Дополнительные сведения об использовании `...` c++ стандарта ISO, см. в разделе [многоточия и шаблоны с переменным числом аргументов](../cpp/ellipses-and-variadic-templates.md) и многоточия и аргументы по умолчанию в [постфиксные выражения](../cpp/postfix-expressions.md).

Параметр, который использует `...` должен быть последним параметром в списке параметров.

## <a name="example"></a>Пример

### <a name="code"></a>Код

```cpp
// mcppv2_paramarray.cpp
// compile with: /clr
using namespace System;
double average( ... array<Int32>^ arr ) {
   int i = arr->GetLength(0);
   double answer = 0.0;

   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];

   return answer / i;
}

int main() {
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));
}
```

```Output
3
```

## <a name="code-example"></a>Пример кода

Приведенный ниже показано, как вызывать в C# функции Visual C++, которая принимает переменное число аргументов.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

Функция `f` могут вызываться из C# или Visual Basic, например, как будто это функция, которая может принимать переменное число аргументов.

В C# аргумент, передаваемый `ParamArray` параметра могут быть вызваны переменное число аргументов. В следующем образце кода находится в C#.

```cs
// mcppv2_paramarray3.cs
// compile with: /r:mcppv2_paramarray2.dll
// a C# program

public class X {
   public static void Main() {
      // Visual C# will generate a String array to match the
      // ParamArray attribute
      C myc = new C();
      myc.f("hello", "there", "world");
   }
}
```

Вызов `f` в Visual C++ можно передать инициализированный массив или массив переменной длины.

```cpp
// mcpp_paramarray4.cpp
// compile with: /clr
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};

int main() {
   C ^ myc = gcnew C();
   myc->f("hello", "world", "!!!");
}
```

## <a name="see-also"></a>См. также

[Массивы](../windows/arrays-cpp-component-extensions.md)