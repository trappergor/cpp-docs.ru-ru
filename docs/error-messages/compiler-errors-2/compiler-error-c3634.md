---
title: "Ошибка компилятора C3634 | Microsoft Docs"
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
  - "C3634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3634"
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

function: в управляемом классе или классе WinRT невозможно определить абстрактный метод  
  
 Абстрактный метод может быть объявлен в управляемом классе или классе WinRT, но он не может быть определен.  
  
 Следующий пример приводит к возникновению ошибки C3634:  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  
  
 **Управляемые расширения для C\+\+**  
  
 Следующий пример приводит к возникновению ошибки C3634:  
  
```  
// C3634b.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
  
__gc class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```