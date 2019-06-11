---
title: Целевые объекты атрибутов (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, targets
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
ms.openlocfilehash: 502f5ba2e5bbb5bd5a5fcceca16acaa3987db4bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516149"
---
# <a name="attribute-targets-ccli-and-ccx"></a>Целевые объекты атрибутов (C++/CLI и C++/CX)

Описатели использования атрибута позволяют определить его целевые объекты.  Каждый атрибут определяется для применения к определенным элементам языка. Например, атрибут может быть определен для применения только для классов и структур.  В приведенном ниже списке показаны возможные синтаксические элементы, для которых можно использовать настраиваемый атрибут. Можно использовать сочетания этих значений (с помощью операций логического ИЛИ).

Чтобы задать целевой объект атрибута, следует при определении атрибута передать один или несколько перечислителей <xref:System.AttributeTargets> объекту <xref:System.AttributeUsageAttribute>.

Ниже приведен список допустимых целевых объектов атрибутов.

- `All` (применяется ко всем конструкциям)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::All)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Assembly` (применяется к сборке в целом)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Assembly)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Module` (применяется к модулю в целом)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Module)]
    ref class Attr : public Attribute {};

    [module:Attr];
    ```

- `Class`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Class)]
    ref class Attr : public System::Attribute {};

    [Attr]   // same as [class:Attr]
    ref class MyClass {};
    ```

- `Struct`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Struct)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [struct:Attr]
    value struct MyStruct{};
    ```

- `enum`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Enum)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [enum:Attr]
    enum struct MyEnum{e, d};
    ```

- `Constructor`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Constructor)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] MyStruct(){}   // same as [constructor:Attr]
    };
    ```

- `Method`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Method)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] void Test(){}   // same as [method:Attr]
    };
    ```

- `Property`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Property)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] property int Test;   // same as [property:Attr]
    };
    ```

- `Field`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Field)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] int Test;   // same as [field:Attr]
    };
    ```

- `Event`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Event)]
    ref class Attr : public Attribute {};

    delegate void ClickEventHandler(int, double);

    ref struct MyStruct{
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]
    };
    ```

- `Interface`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Interface)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [event:Attr]
    interface struct MyStruct{};
    ```

- `Parameter`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Parameter)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    void Test([Attr] int i);
    void Test2([parameter:Attr] int i);
    };
    ```

- `Delegate`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Delegate)]
    ref class Attr : public Attribute {};

    [Attr] delegate void Test();
    [delegate:Attr] delegate void Test2();
    ```

- `ReturnValue`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::ReturnValue)]
    ref class Attr : public Attribute {};

    ref struct MyStruct {
    // Note required specifier
    [returnvalue:Attr] int Test() { return 0; }
    };
    ```

Обычно атрибут непосредственно предшествует элементу языка, к которому он применяется. Однако в некоторых случаях позиции атрибута недостаточно для определения предполагаемого целевого объекта. Рассмотрим следующий пример.

```cpp
[Attr] int MyFn(double x)...
```

Синтаксически не существует способа определить, должен ли атрибут применяться к методу или к возвращаемому значению метода (в этом случае по умолчанию атрибут применяется к методу). В таких случаях можно использовать описатель применения атрибута. Например, чтобы атрибут применялся к возвращаемому значению, используйте описатель `returnvalue` следующим образом:

```cpp
[returnvalue:Attr] int MyFn(double x)... // applies to return value
```

Описатели использования атрибута необходимы в следующих случаях.

- Для задания атрибута уровня сборки или модуля.

- Для указания того, что атрибут применяется к возвращаемому значению метода, а не к методу:

    ```cpp
    [method:Attr] int MyFn(double x)...     // Attr applies to method
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value
    [Attr] int MyFn(double x)...            // default: method
    ```

- Для указания того, что атрибут применяется к методу доступа свойства, а не к свойству:

    ```cpp
    [method:MyAttr(123)] property int Property()
    [property:MyAttr(123)] property int Property()
    [MyAttr(123)] property int get_MyPropy() // default: property
    ```

- Для указания того, что атрибут применяется к методу доступа события, а не к событию:

    ```cpp
    delegate void MyDel();
    ref struct X {
       [field:MyAttr(123)] event MyDel* MyEvent;   //field
       [event:MyAttr(123)] event MyDel* MyEvent;   //event
       [MyAttr(123)] event MyDel* MyEvent;   // default: event
    }
    ```

Описатель использования атрибута применяется только к атрибуту, который следует сразу за ним; то есть

```cpp
[returnvalue:Attr1, Attr2]
```

отличается от

```cpp
[returnvalue:Attr1, returnvalue:Attr2]
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В этом примере показано задание нескольких целевых объектов.

### <a name="code"></a>Код

```cpp
using namespace System;
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Struct, AllowMultiple = true )]
ref struct Attr : public Attribute {
   Attr(bool i){}
   Attr(){}
};

[Attr]
ref class MyClass {};

[Attr]
[Attr(true)]
value struct MyStruct {};
```

## <a name="see-also"></a>См. также

[Пользовательские атрибуты](user-defined-attributes-cpp-component-extensions.md)