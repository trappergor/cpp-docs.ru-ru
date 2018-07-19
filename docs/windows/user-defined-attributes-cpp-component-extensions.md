---
title: Пользовательские атрибуты (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22f8dfa7e78568f100b0c58c881b9e84cb47a149
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891770"
---
# <a name="user-defined-attributes--c-component-extensions"></a>Пользовательские атрибуты (расширения компонентов C++)
Настраиваемые атрибуты позволяют расширять метаданные интерфейса, класса или структуры, метода, параметра или перечисления.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 Настраиваемые атрибуты поддерживаются всеми средами выполнения.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Атрибуты C++/CX поддерживают только свойства; конструкторы атрибутов и методы не поддерживаются.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
 Настраиваемые атрибуты позволяют расширять метаданные управляемого элемента. Дополнительные сведения см. в разделе [Атрибуты](/dotnet/standard/attributes/index).  
  
### <a name="remarks"></a>Примечания  
 Сведения и синтаксис, представленный в этом разделе предназначены для замены сведения, представленные в [атрибут](../windows/attribute.md).  
  
 Настраиваемый атрибут можно определить, указав тип и создав для него базовый класс <xref:System.Attribute>, а также при необходимости применив атрибут <xref:System.AttributeUsageAttribute>.  
  
 Например, на сервере транзакций Microsoft Transaction Server (MTS) 1.0 поведение по отношению к транзакциям, синхронизации, распределению нагрузки и т. д. было задано с помощью пользовательских идентификаторов GUID, вставленных в библиотеку типов посредством настраиваемого атрибута ODL. Следовательно, клиент сервера MTS может определить его характеристики, считав библиотеку типов. В .NET Framework аналогом библиотеки типов являются метаданные, а аналогом настраиваемого атрибута ODL — настраиваемые атрибуты. Кроме того, чтение библиотеки типов аналогично использованию отражения на типы.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Целевые объекты атрибутов](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Типы параметров атрибутов](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Сведения о подписи сборок в Visual C++ см. в разделе [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере показано определение настраиваемого атрибута.  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 **Пример**  
  
 В приведенном ниже примере продемонстрированы некоторые важные возможности настраиваемых атрибутов. Например, в нем показано общее использование настраиваемых атрибутов: создание экземпляра сервера, который может полностью представлять свои характеристики клиентам.  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **Вывод**  
  
```Output  
Service Priority = 0  
  
Service Access = Write  
  
Service Priority = 3  
  
Service Access = Write  
  
Service Priority = 1  
  
Service Access = Read  
```  
  
 **Пример**  
  
 Тип Object^ заменяет тип данных variant. В следующем примере определяется настраиваемый атрибут, который принимает массив Object^ в качестве параметров.  
  
 Аргументы атрибута должны быть константами времени компиляции; в большинстве случаев они должны быть константными литералами.  
  
 В разделе [typeid](../windows/typeid-cpp-component-extensions.md) сведения о том, как вернуть значение System::Type из блоке настраиваемых атрибутов.  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 **Пример**  
  
 Среда выполнения требует, чтобы открытая часть класса настраиваемого атрибута была сериализуемой.  При создании настраиваемых атрибутов их именованные аргументы ограничены константами времени компиляции.  (Можно сказать, что к макету класса в метаданных добавляется последовательность битов.)  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)