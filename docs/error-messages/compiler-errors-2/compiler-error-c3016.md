---
title: "Ошибка компилятора C3016 | Microsoft Docs"
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
  - "C3016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3016"
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": переменная индекса в операторе For директивы OpenMP должна иметь тип целого со знаком  
  
 Переменная индекса в операторе `for` директивы OpenMP должна иметь целочисленный тип со знаком.  
  
 Следующий пример приводит к возникновению ошибки C3016:  
  
```  
// C3016.cpp // compile with: /openmp int main() { #pragma omp parallel { unsigned int i = 0; // Try the following line instead: // int i = 0; #pragma omp for for (i = 0; i <= 10; ++i)   // C3016 { } } }  
```