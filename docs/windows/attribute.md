---
title: атрибут | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.attribute
dev_langs:
- C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62eabc9eb9b2043fe3d66389d56b1995afcd57e7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212251"
---
# <a name="attribute"></a>Атрибут

Позволяет создавать настраиваемый атрибут.

## <a name="syntax"></a>Синтаксис

```cpp
[ attribute(
   AllowOn,
   AllowMultiple=boolean,
   Inherited=boolean
) ]
```

### <a name="parameters"></a>Параметры

*AllowOn*  
Указывает элементы языка, к которым можно применять настраиваемый атрибут. Значение по умолчанию — `System::AttributeTargets::All` (см. в разделе [System::AttributeTargets](https://msdn.microsoft.com/library/system.attributetargets.aspx)).

*AllowMultiple*  
Указывает ли настраиваемый атрибут может применяться многократно конструкции. Значение по умолчанию — FALSE.

*Унаследованные*  
Указывает, является ли атрибут наследуются подклассами. Компилятор не поддерживает специальные для использования этой функции; Это задание атрибута получатели (`Reflection`, например) следует учитывать эти сведения. Если *унаследованное* имеет значение TRUE, атрибут наследуется. Если *AllowMultiple* имеет значение TRUE, атрибут будет накапливаться в производный член; Если *AllowMultiple* имеет значение FALSE, атрибут будет переопределить (или замена) в наследовании. Если *унаследованное* имеет значение FALSE, атрибут не наследуется. Значение по умолчанию — TRUE.

## <a name="remarks"></a>Примечания

> [!NOTE]
> **Атрибут** атрибут считается устаревшим.  Использовать общий атрибут среды выполнения языка `System.Attribute` к непосредственно для создания пользовательских attirbutes. Дополнительные сведения см. в разделе [определяемые пользователем атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md).

Вы определите [настраиваемого атрибута](../windows/custom-attributes-cpp.md) , поместив **атрибут** атрибута в определении управляемого класса или структуры. Имя класса является настраиваемого атрибута. Пример:

```cpp
[ attribute(Parameter) ]
public ref class MyAttr {};
```

Определяет атрибут, именуемый `MyAttr` , которые могут быть применены для параметров функции. Класс должен быть открытым, если атрибут будет использоваться в других сборках.

> [!NOTE]
> Во избежание конфликтов пространств имен, все имена атрибутов неявно заканчиваются словом «Attribute»; в этом примере атрибут и класс называется фактически `MyAttrAttribute`, но `MyAttr` и `MyAttrAttribute` взаимозаменяемы.

Открытые конструкторы класса определения атрибута неименованные параметры. Перегруженные конструкторы разрешить несколько способов указания атрибута, чтобы настраиваемый атрибут, определенный следующим образом:

```cpp
// cpp_attr_ref_attribute.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes
public ref class MyAttr {
public:
   MyAttr() {}   // Constructor with no parameters
   MyAttr(int arg1) {}   // Constructor with one parameter
};

[MyAttr]
ref class ClassA {};   // Attribute with no parameters

[MyAttr(123)]
ref class ClassB {};   // Attribute with one parameter
```

Открытые элементы данных и свойства класса являются необязательно именованные параметры атрибута:

```cpp
// cpp_attr_ref_attribute_2.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class) ]
ref class MyAttr {
public:
   // Property Priority becomes attribute's named parameter Priority
    property int Priority {
       void set(int value) {}
       int get() { return 0;}
   }
   // Data member Version becomes attribute's named parameter Version
   int Version;
   MyAttr() {}   // constructor with no parameters
   MyAttr(int arg1) {}   // constructor with one parameter
};

[MyAttr(123, Version=2)]
ref class ClassC {};
```

Список допустимых типов параметров, см. в разделе [пользовательские атрибуты](../windows/custom-attributes-cpp.md).

См. в разделе [определяемые пользователем атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md) обсуждение целевые объекты атрибутов.

**Атрибут** атрибут имеет *AllowMultiple* параметр, указывающий, является ли настраиваемый атрибут однократного использования или multiuse, (могут отображаться несколько раз на ту же сущность).

```cpp
// cpp_attr_ref_attribute_3.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]
ref struct MyAttr {
   MyAttr(){}
};   // MyAttr is a multiuse attribute

[MyAttr, MyAttr()]
ref class ClassA {};
```

Классы настраиваемых атрибутов являются производными от прямо или косвенно <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, который упрощает задание определений атрибутов в метаданных и быстро. **Атрибут** атрибут подразумевает наследование от `System::Attribute`, поэтому нет необходимости явных наследование:

```cpp
[ attribute(Class) ]
ref class MyAttr
```

эквивалентно

```cpp
[ attribute(Class) ]
ref class MyAttr : System::Attribute   // OK, but redundant.
```

**атрибут** является псевдонимом для <xref:System.AttributeUsageAttribute?displayProperty=fullName> (не атрибут; это исключение из правила именования атрибут).

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс ссылки**, **структура ссылки**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_attribute_4.cpp
// compile with: /c /clr
using namespace System;
[attribute(AttributeTargets::Class)]
ref struct ABC {
   ABC(Type ^) {}
};

[ABC(String::typeid)]   // typeid operator yields System::Type ^
ref class MyClass {};
```

## <a name="example"></a>Пример

`Inherited` Именованный аргумент указывает ли настраиваемый атрибут, примененный в базовом классе будет отображаться на отражении производного класса.

```cpp
// cpp_attr_ref_attribute_5.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;

[attribute( AttributeTargets::Method, Inherited=false )]
ref class BaseOnlyAttribute { };

[attribute( AttributeTargets::Method, Inherited=true )]
ref class DerivedTooAttribute { };

ref struct IBase {
public:
   [BaseOnly, DerivedToo]
   virtual void meth() {}
};

// Reflection on Derived::meth will show DerivedTooAttribute
// but not BaseOnlyAttribute.
ref class Derived : public IBase {
public:
   virtual void meth() override {}
};

int main() {
   IBase ^ pIB = gcnew Derived;

   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );
   Console::WriteLine( pObjs->Length ) ;
}
```

```Output
2
```

## <a name="see-also"></a>См. также

[Алфавитный указатель атрибутов](../windows/attributes-alphabetical-reference.md)  
[Настраиваемые атрибуты](https://msdn.microsoft.com/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)