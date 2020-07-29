---
title: Типы параметров атрибутов (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: c7b219ddad939aab7d6093787dc2fe4131ccced5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225167"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Типы параметров атрибутов (C++/CLI и C++/CX)

Значения, передаваемые в атрибуты, должны быть известны компилятору во время компиляции.  Параметры атрибутов могут быть следующих типов:

- **`bool`**

- **`char`**, **`unsigned char`**

- **`short`**, **`unsigned short`**

- **`int`**, **`unsigned int`**

- **`long`**, **`unsigned long`**

- **`__int64`**, **неподписанный __int64**

- **`float`**, **`double`**

- **`wchar_t`**

- **`char*`** или `wchar_t*` или`System::String*`

- `System::Type ^`

- `System::Object ^`

- **`enum`**

## <a name="example"></a>Пример

### <a name="code"></a>Код

```cpp
// attribute_parameter_types.cpp
// compile with: /clr /c
using namespace System;
ref struct AStruct {};

[AttributeUsage(AttributeTargets::ReturnValue)]
ref struct Attr : public Attribute {
   Attr(AStruct ^ i){}
   Attr(bool i){}
   Attr(){}
};

ref struct MyStruct {
   static AStruct ^ x = gcnew AStruct;
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104
   [returnvalue:Attr] int Test2() { return 0; }   // OK
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK
};
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

При определении атрибутов все неименованные (позиционные) аргументы должны предшествовать любым именованным аргументам.

### <a name="code"></a>Код

```cpp
// extending_metadata_c.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // No arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // Named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Параметры атрибутов могут быть одномерными массивами указанных выше типов.

### <a name="code"></a>Код

```cpp
// extending_metadata_d.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="see-also"></a>См. также статью

[Определяемые пользователем атрибуты](user-defined-attributes-cpp-component-extensions.md)
