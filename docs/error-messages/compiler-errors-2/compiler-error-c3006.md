---
title: "Ошибка компилятора C3006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3006"
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"предложение": в предложении директивы OpenMP "директива" отсутствует необходимый аргумент  
  
 В директиве OpenMP отсутствует ожидаемый аргумент.  
  
 Следующий пример приводит к возникновению ошибки C3006:  
  
```  
// C3006.c // compile with: /openmp int main() { #pragma omp parallel shared   // C3006 // Try the following line instead: // #pragma omp parallel shared(x) {} }  
```