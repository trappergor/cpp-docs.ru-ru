---
title: "Пользовательские атрибуты (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "настраиваемые атрибуты, расширение метаданных"
  - "метаданные, расширение"
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пользовательские атрибуты (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Настраиваемые атрибуты позволяют расширять метаданные интерфейса, класса или структуры, метода, параметра или перечисления.  
  
## Все среды выполнения  
 Все среды выполнения поддерживают настраиваемые атрибуты.  
  
## среда выполнения Windows  
 Атрибуты C\+\+\/CX поддерживают только свойства, но не конструкторы атрибутов или методы.  
  
### Примечания  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 Настраиваемые атрибуты позволяют расширять метаданные управляемого элемента.  Для получения дополнительной информации см. [Атрибуты](../Topic/Extending%20Metadata%20Using%20Attributes.md).  
  
### Примечания  
 Сведения и синтаксис, представленные в этом разделе, заменяют сведения, представленные в разделе [attribute](../windows/attribute.md).  
  
 Можно указать настраиваемый атрибут, указав тип и создав базовый класс <xref:System.Attribute> для типа, и при необходимости, применив атрибут <xref:System.AttributeUsageAttribute>.  
  
 Например, на сервере транзакций Microsoft Transaction Server \(MTS\) 1.0, поведение по отношению к транзакциям, синхронизации, распределению нагрузки и т.д. было задано с помощью вставки пользовательских GUID в библиотеку типов при помощи настраиваемого атрибута ODL.  Следовательно, клиент сервера MTS может определить его характеристики, считывая библиотеку типов.  В платформе .NET Framework аналогом библиотеки типов являются метаданные, и аналогом настраиваемого атрибута ODL являются настраиваемые атрибуты.  Также чтение библиотеки типов аналогично использованию отражения на типы.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Целевые объекты атрибутов](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Типы параметров атрибутов](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Сведения о подписи сборок в проектах Visual C\+\+ содержатся в разделе [Сборки со строгими именами \(подписывание сборок\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере представлен способ определения настраиваемого атрибута.  
  
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
  
 В следующем примере показаны некоторые важные особенности настраиваемых атрибутов.  Например, в этом примере показано использование настраиваемых атрибутов: создание экземпляра сервера, который может полностью описать себя клиентам.  
  
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
  
 **Output**  
  
  **Service Priority \= 0**  
 **Service Access \= Write**  
 **Service Priority \= 3**  
 **Service Access \= Write**  
 **Service Priority \= 1**  
 **Service Access \= Read** **Пример**  
  
 Тип Object^ заменяет тип данных variant.  В следующем примере определяется настраиваемый атрибут, который принимает массив Object^ в качестве параметров.  
  
 Аргументы атрибута должны являться константами время компиляции; в большинстве случаев они должны быть константными литералами.  
  
 Сведения о возврате значения типа System::Type из блока настраиваемых атрибутов см. в разделе [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md).  
  
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
  
 Среда выполнения требует, чтобы открытая часть класса настраиваемого атрибута была сериализуема.  При создании настраиваемых атрибутов, именованные аргументы настраиваемого атрибута ограничены константными выражениями времени компиляции.  \(Можно сказать, что к метаданным в структуре класса добавляется последовательность битов.\)  
  
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
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)