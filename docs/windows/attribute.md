---
title: атрибут | Документы Microsoft
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
ms.openlocfilehash: 9826b689e2b8a640efe66e8625b97b3cec347acf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="attribute"></a>Атрибут
Можно создать пользовательский атрибут.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *AllowOn*  
 Указывает элементы языка, к которым можно применять этот настраиваемый атрибут. Значение по умолчанию — **System::AttributeTargets::All** (см. [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)).  
  
 `AllowMultiple`  
 Указывает, является ли пользовательский атрибут может применяться многократно конструкции. Значение по умолчанию — **FALSE**.  
  
 `Inherited`  
 Указывает, является ли атрибут наследуются подклассами. Компилятор не поддерживает специальные для этой функции. Это задание атрибута потребителей (например, посредством) следует использовать эти сведения. Если `Inherited` — **TRUE**, атрибут наследуется. Если `AllowMultiple` — **TRUE**, атрибут накапливаются на производный член; Если `AllowMultiple` — **FALSE**, атрибут будет переопределить (или заменить) в наследовании. Если `Inherited` — **FALSE**, атрибут не наследуется. Значение по умолчанию — **TRUE**.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  `attribute` Атрибут считается устаревшим.  Используйте общий атрибут среды выполнения языка System.Attribute непосредственно для создания определяемых пользователем attirbutes.  Дополнительные сведения см. в разделе [определяемые пользователем атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Можно определить [настраиваемого атрибута](../windows/custom-attributes-cpp.md) , поместив `attribute` атрибута в определении управляемого класса или структуры. Имя класса является настраиваемого атрибута. Пример:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 Определяет атрибут с именем MyAttr, которая может применяться для параметров функции. Класс должен быть открытым, если атрибут будет использоваться в других сборках.  
  
> [!NOTE]
>  Во избежание конфликтов пространств имен, все имена атрибутов неявно заканчиваться «Атрибут»; в этом примере имя атрибута и класса фактически MyAttrAttribute, но MyAttr и MyAttrAttribute взаимозаменяемы.  
  
 Открытые конструкторы класса определения атрибута неименованные параметры. Перегруженные конструкторы разрешить несколько способов указания атрибута, поэтому пользовательский атрибут, который будет определена следующим образом:  
  
```  
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
  
 Открытые члены данных и свойства класса, необязательно именованных параметров атрибута:  
  
```  
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
  
 Список типов параметров возможно атрибута см. в разделе [пользовательских атрибутов](../windows/custom-attributes-cpp.md).  
  
 В разделе [определяемые пользователем атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md) обсуждение целевые объекты атрибутов.  
  
 `attribute` Атрибут имеет `AllowMultiple` параметр, который указывает, является ли настраиваемый атрибут однократного использования или различают серверы многопользовательские (может использоваться более чем один раз на той же сущности).  
  
```  
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
  
 Настраиваемый атрибут классы являются производными прямо или косвенно <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, какие упрощает определение определений атрибутов в метаданных быстрый и простой. `attribute` Атрибут задает наследование от System::Attribute, явное наследование не не требуется:  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 эквивалентно  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` является псевдонимом для <xref:System.AttributeUsageAttribute?displayProperty=fullName> (AttributeAttribute; это исключение из правила именования атрибута).  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`ref` **Класс**, **структура ссылки**|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Пример  
  
```  
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
 `Inherited` Именованный аргумент указывает, является ли настраиваемый атрибут, примененный на базовом классе будут отображаться на отражение производного класса.  
  
```  
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
 [Настраиваемые атрибуты](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)