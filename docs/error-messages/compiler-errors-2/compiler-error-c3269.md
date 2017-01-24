---
title: "Ошибка компилятора C3269 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3269"
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

function: функцию\-член управляемого типа или типа WinRT нельзя объявить с помощью "..."  
  
 Функции\-члены управляемого класса и класса WinRT не могут объявлять списки параметров переменной длины.  
  
 В следующем примере показано возникновение ошибки C3269 и приводятся сведения по ее устранению.  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
 В следующем примере показано возникновение ошибки C3269 и приводятся сведения по ее устранению.  
  
```  
// C3269.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```