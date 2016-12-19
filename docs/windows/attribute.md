---
title: "attribute | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.attribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof keyword"
  - "custom attributes, creating"
  - "attribute attribute"
  - "attributes [C++], custom"
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет создать настраиваемый атрибут.  
  
## Синтаксис  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### Параметры  
 *AllowOn*  
 Определяет элементы языка, к которым настраиваемый атрибут можно применить.  Значение по умолчанию **System:: AttributeTargets:: Все** \(см.  [System:: AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)\).  
  
 `AllowMultiple`  
 Определяет, является ли настраиваемый атрибут может быть применен к конструкции повторно.  Значение по умолчанию **False**.  
  
 `Inherited`  
 Указывает ли атрибут быть унаследованным подклассами.  Компилятор не предоставляет никаких специальную поддержку этой функциональности; задание объектов\-получателей атрибута \(отражения, например учитывать эти сведения.  If `Inherited` существует  **True**атрибут унаследован.  If `AllowMultiple` существует  **True**атрибут накапливает в производном элементе; If  `AllowMultiple` существует  **False**атрибут переопределяет \(или заменить\) в наследовании.  If `Inherited` существует  **False**атрибут не является унаследованным.  Значение по умолчанию **True**.  
  
## Заметки  
  
> [!NOTE]
>  `attribute` атрибут теперь нерекомендуем.  Используйте атрибут System.Attribute среды CLR в непосредственно для создания определяемых пользователем attirbutes.  Дополнительные сведения см. в разделе [Пользовательские атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Указании a [настраиваемый атрибут](../windows/custom-attributes-cpp.md) устанавливая  `attribute` атрибут управляемом определении класса или структуры.  Имя класса настраиваемого атрибута.  Примеры.  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 определяет атрибут с именем MyAttr, которое можно применять для функционирования параметры.  Класс должен быть открытым, если атрибут планируется использовать в других сборках.  
  
> [!NOTE]
>  Во избежание конфликтов пространств имен, все имена атрибутов явно заканчивается на "атрибутом"; в этом примере имя атрибута и класс, но фактически MyAttrAttribute MyAttr и MyAttrAttribute можно использовать взаимозаменимо.  
  
 Открытые конструкторы типа задают параметры атрибута неименованные.  Перегруженные конструкторы предоставляют различные способы указания атрибута, чтобы настраиваемый атрибут, который определен следующим образом:  
  
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
  
 Элементы данных и открытые свойства типа с именем необязательно атрибута параметрами:  
  
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
  
 Список возможных типов параметров атрибутов см. в разделе [Пользовательские атрибуты](../windows/custom-attributes-cpp.md).  
  
 См. [Пользовательские атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md) обсуждение в целевых объектах атрибута.  
  
 `attribute` атрибут имеющий  `AllowMultiple` параметр, который определяет, является ли настраиваемый атрибут одна использование или multiuse \(может появляться более одного раза в одну и ту же сущность\).  
  
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
  
 Классы настраиваемого атрибута получаются напрямую или косвенно от <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, который упрощает определение определения атрибута в метаданных легко и быстро.  `attribute` атрибут указывает наследование из system:: Точный атрибут, поэтому вывод не требуются.  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 , эквивалентно выражению  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` псевдоним  <xref:System.AttributeUsageAttribute?displayProperty=fullName> \(не AttributeAttribute; это исключением из правила именования атрибута\).  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`ref` **класс**"  **структура ref**|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## Пример  
  
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
  
## Пример  
 `Inherited` именованные аргументы определяют, будет ли настраиваемый атрибут, примененный в базовом классе вверх на отражении производного класса.  
  
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
  
  **2**   
## См. также  
 [Attributes Alphabetical Reference](../windows/attributes-alphabetical-reference.md)   
 [Custom Attributes](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)