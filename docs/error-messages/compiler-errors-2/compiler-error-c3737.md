---
title: "Ошибка компилятора C3737 | Microsoft Docs"
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
  - "C3737"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3737"
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3737
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"делегат": делегат не может использовать явное соглашение о вызове  
  
 Для [\_\_delegate](../Topic/__delegate.md) нельзя задать [соглашение о вызове](../Topic/Calling%20Conventions.md).  
  
 Следующий пример приводит к возникновению ошибки C3737:  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3737:  
  
```  
// C3737b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// __delegate void MyFunc();  
  
int main() {  
}  
```