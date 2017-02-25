---
title: "Ошибка компилятора C3414 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3414"
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": не удается определить импортированную функцию\-член  
  
 В коде определен член, который уже определен в связанной сборке.  
  
 Следующий пример приводит к возникновению ошибки C3414:  
  
```  
// C3414a2.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 а затем:  
  
```  
// C3414b2.cpp  
// compile with: /clr  
#using <C3414a2.dll>  
  
void MyClass::Test() {    // C3414  
}  
  
System::Object::Object() {    // C3414  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3414:  
  
```  
// C3414a.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
public __gc class MyClass  
{  
public:  
   void Test(){}  
};  
```  
  
 а затем:  
  
```  
// C3414b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
#using <C3414a.dll>  
  
void MyClass::Test()  
{    // C3414  
}  
  
System::Object::Object()  
{    // C3414  
}  
```