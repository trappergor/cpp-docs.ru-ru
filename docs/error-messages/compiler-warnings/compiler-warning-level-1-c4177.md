---
title: "Предупреждение компилятора (уровень 1) C4177 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4177"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4177"
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4177
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

прагма \#pragma должна быть в глобальной области  
  
 Прагма [Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) не должна использоваться в локальной области. Прагма **pragma** будет недействительна до появления глобальной области после текущей области.  
  
 В следующем примере возникает ошибка C4177:  
  
```  
// C4177.cpp // compile with: /W1 // #pragma bss_seg("global")   // OK int main() { #pragma bss_seg("local")    // C4177 }  
```