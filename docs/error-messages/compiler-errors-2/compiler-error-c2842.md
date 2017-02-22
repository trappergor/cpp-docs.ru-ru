---
title: "Ошибка компилятора C2842 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2842"
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка компилятора C2842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

class: управляемый тип или тип WinRT не может определять свой собственный operator new или operator delete  
  
 Можно определить собственные операторы [new](../Topic/operator%20new%20\(%3Cnew%3E\).md) и [delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) для управления выделением памяти в неуправляемой куче.  Однако эти операторы не могут быть определены в ссылочных классах , так как только они выделяются в управляемой куче.  
  
 Дополнительные сведения см. в разделе [Пользовательские операторы](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2842:  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2842:  
  
```  
// C2842_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```