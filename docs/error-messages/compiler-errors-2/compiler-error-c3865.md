---
title: "Ошибка компилятора C3865 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3865"
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"соглашение\_о\_вызовах" : может использоваться только в машинных функциях\-членах  
  
 Соглашение о вызовах использовалось либо в глобальной функции, либо в управляемой функции\-члене.  Соглашение о вызовах может использоваться только в машинной \(неуправляемой\) функции\-члене.  
  
 Дополнительные сведения см. в разделе [Соглашения о вызовах](../Topic/Calling%20Conventions.md).  
  
 Следующий пример приводит к возникновению ошибки C3865:  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```