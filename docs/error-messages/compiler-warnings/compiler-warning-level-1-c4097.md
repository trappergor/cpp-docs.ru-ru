---
title: "Предупреждение компилятора (уровень&#160;1) C4097 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4097"
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

требуется параметр директивы pragma: "restore" или "off"  
  
 В прагму передано недопустимое значение.  
  
 В следующем примере возникает ошибка C4097:  
  
```  
// C4097.cpp // compile with: /W1 #pragma runtime_checks("",test)   // C4097 // try the following line instead // #pragma runtime_checks("",off) int main() { }  
```