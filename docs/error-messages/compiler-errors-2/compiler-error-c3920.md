---
title: "Ошибка компилятора C3920 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3920"
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator": не удается определить постфиксный оператор WinRT или CLR инкремента или декремента. При вызове постфиксного оператора WinRT или CLR произойдет вызов соответствующего префиксного оператора WinRT или CLR \(op\_Increment\/op\_Decrement\), но с постфиксной семантикой  
  
 Среда выполнения Windows и среда CLR не поддерживают постфиксный оператор, а пользовательские постфиксные операторы не разрешены.  Можно определить префиксный оператор, который будет использоваться для операций до и после приращения.  
  
 В следующем примере показано возникновение ошибки C3920 и приводятся сведения по ее устранению.  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```