---
title: Типы параметров атрибутов (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: cf33014c455bef145f7b7ec7ee353f27d1157f24
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008607"
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

- **`char*`** или `wchar_t*` или `System::String*`

- `System::Type ^`

- `System::Object ^`

- **`enum`**

## <a name="example-attribute-parameter-types"></a>Пример: типы параметров атрибутов

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

## <a name="example-unnamed-arguments-precede-named-arguments"></a>Пример: безымянные аргументы предшествуют именованным аргументам

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

## <a name="example-one-dimensional-array-attribute-parameter"></a>Пример: параметр атрибута одномерные массивов

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

## <a name="see-also"></a>См. также

[Определяемые пользователем атрибуты](user-defined-attributes-cpp-component-extensions.md)
