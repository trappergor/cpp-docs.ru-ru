---
title: "Ошибка компилятора C3009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3009"
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метка": переход в структурированный блок OpenMP не разрешен  
  
 Код не может переходить в блок OpenMP или из этого блока.  
  
 В следующем примере возникает ошибка C3009:  
  
```  
// C3009.c // compile with: /openmp int main() { #pragma omp parallel { lbl2:; } goto lbl2;   // C3009 }  
```