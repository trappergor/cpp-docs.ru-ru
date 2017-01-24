---
title: "Ошибка компилятора C3004 | Microsoft Docs"
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
  - "C3004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3004"
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"предложение": предложение не допускается в директиве OpenMP "директива"  
  
 Предложение OpenMP используется в директиве, для которой оно не включено.  
  
 Следующий пример приводит к возникновению ошибки C3004:  
  
```  
// C3004.c // compile with: /openmp int main() { int x, y, z; // Shared clause not allowed for 'single' directive. #pragma omp single shared(x, y)   // C3004 x = y; }  
```