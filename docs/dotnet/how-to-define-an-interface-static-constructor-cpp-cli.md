---
title: "Практическое руководство. Определение статического конструктора интерфейса (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "конструкторы [C++]"
  - "статический конструктор интерфейса"
  - "статические конструкторы, интерфейс"
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Определение статического конструктора интерфейса (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Интерфейс может быть статический конструктор, который можно использовать для инициализации статические члены данных.  Вызывается не более одного раза, и вызывает статический конструктор ранее в первый раз статический член интерфейса осуществляется доступ.  
  
 Дополнительные сведения о статических конструкторах см. в разделе [Практическое руководство. Определение статических конструкторов в классе или структуре](../misc/how-to-define-static-constructors-in-a-class-or-struct.md).  
  
## Пример  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
  **в статическом конструкторе MyInterface**  
**99**  
**99**  
**99**   
## См. также  
 [interface class](../windows/interface-class-cpp-component-extensions.md)