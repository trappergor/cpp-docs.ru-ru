---
title: "Ошибка компилятора C2196 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2196"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2196"
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2196
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

значение варианта "значение" уже используется  
  
 Оператор switch использует то же значение варианта более одного раза.  
  
 В следующем примере возникает ошибка C2196:  
  
```  
// C2196.cpp int main() { int i = 0; switch( i ) { case 0: break; case 0:   // C2196 // try the following line instead // case 1: break; } }  
```