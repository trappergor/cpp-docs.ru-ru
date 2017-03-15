---
title: "auto_gcroot::attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.attach"
  - "auto_gcroot::attach"
  - "msclr::auto_gcroot::attach"
  - "msclr.auto_gcroot.attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::attach"
ms.assetid: 996ede65-bcb5-41f2-bfbf-507f8a578241
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# auto_gcroot::attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вложение `auto_gcroot` к объекту.  
  
## Синтаксис  
  
```  
auto_gcroot<_element_type> & attach(  
   _element_type _right  
);  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### Параметры  
 `_right`  
 Объект в вложению, или `auto_gcroot`, содержащий объект к вложению.  
  
## Возвращаемое значение  
 Текущий объект `auto_gcroot`.  
  
## Заметки  
 Если `_right``auto_gcroot`, оно владение выпусков его объекта до вложен в текущий объект `auto_gcroot`.  
  
## Пример  
  
```  
// msl_auto_gcroot_attach.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
   a.attach( gcnew ClassA( "second" ) ); // attach same type  
   a->PrintHello();  
   ClassA^ ha = gcnew ClassA( "third" );  
   a.attach( ha ); // attach raw handle  
   a->PrintHello();  
   auto_gcroot<ClassB^> b( gcnew ClassB("fourth") );  
   b->PrintHello();  
   a.attach( b ); // attach derived type  
   a->PrintHello();  
}  
```  
  
  **в конструкторе ClassA: сначала**  
**Hello от первого суффикса\!**  
**в конструкторе ClassA: second**  
**в деструкторе ClassA: сначала**  
**Hello из второго суффикса\!**  
**в конструкторе ClassA: третье**  
**в деструкторе ClassA: second**  
**Hello из третьего суффикса\!**  
**в конструкторе ClassA: четвертое**  
**Hello\! из четвертого B**  
**в деструкторе ClassA: третье**  
**Hello из четвертого суффикса\!**  
**в деструкторе ClassA: четвертое**   
## Требования  
 **Файл заголовка**\<msclr\\auto\_gcroot.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [Члены auto\_gcroot](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::operator\=](../dotnet/auto-gcroot-operator-assign.md)   
 [auto\_gcroot::release](../dotnet/auto-gcroot-release.md)