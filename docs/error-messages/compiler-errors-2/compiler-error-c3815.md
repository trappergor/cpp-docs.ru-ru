---
title: "Ошибка компилятора C3815 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3815"
ms.assetid: c5a3b404-6341-4fd3-92af-152b404c4dde
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

тип возвращаемого значения метода доступа "get\_accessor" должен соответствовать типу последнего параметра метода доступа "set"  
  
 В объявлениях [свойств](../../misc/property.md) тип возвращаемого значения метода `get_accessor` должен соответствовать последнему параметру в объявлении метода доступа "set".  
  
 Ошибка C3815 возникает только при использовании параметра **\/clr:oldSyntax**.  
  
 Следующий пример приводит к возникновению ошибки C3815:  
  
```  
// C3815.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc class X  
{  
public:  
   __property char get_N()  
   // try the following line instead  
   // __property int get_N()  
   {  
      return m_val;  
   }  
  
   __property void set_N( int val)  
   {  
      m_val = val;  
   }  
  
private:  
   int m_val;  
};   // C3815  
```  
  
 В следующем примере демонстрируется перегрузка свойств, позволяющая использовать различные типы для возвращаемого значения "get" и последнего параметра "set":  
  
```  
// C3815b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
public __gc class MyClass {  
public:  
// 1st property:  
   __property System::Int32 get_p1();  
   __property void set_p1(System::Int32 i);  
  
// 2nd property (only setter):  
   __property void set_p1(System::Int32* i);  
  
};  
```