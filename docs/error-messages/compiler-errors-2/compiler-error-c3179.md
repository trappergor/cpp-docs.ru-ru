---
title: "Ошибка компилятора C3179 | Microsoft Docs"
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
  - "C3179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3179"
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неименованный управляемый тип или тип WinRT не допускается  
  
 Все классы и структуры среды CLR и WinRT должны иметь имена.  
  
 В следующем примере показано возникновение ошибки C3179 и приводятся сведения по ее устранению.  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  
  
 В следующем примере показано возникновение ошибки C3179 и приводятся сведения по ее устранению.  
  
```  
// C3179b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
typedef __value struct {   // C3179  
// try the following line instead  
// typedef __value struct MyStruct {  
   int i;  
} V;  
```