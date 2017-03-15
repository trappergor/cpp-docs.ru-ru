---
title: "Ошибка компилятора C3059 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3059"
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var: символ threadprivate нельзя использовать в предложении "предложение"  
  
 Символ [threadprivate](../Topic/threadprivate.md) использовался в предложении.  
  
 В следующем примере возникает ошибка C3059:  
  
```  
// C3059.cpp // compile with: /openmp #include "omp.h" int x, y; #pragma omp threadprivate(x, y) int main() { #pragma omp parallel private(x, y)   // C3059 { x = y; } }  
```  
  
 Возможное решение:  
  
```  
// C3059b.cpp // compile with: /openmp #include "omp.h" int x = 0, y = 0; int main() { #pragma omp parallel firstprivate(y) private(x) { x = y; } }  
```