---
title: "Ошибка компилятора C3058 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3058"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3058"
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3058
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": символ не объявлен как threadprivate до его использования в предложении copyin  
  
 Символ нужно сначала объявить как [threadprivate](../Topic/threadprivate.md) перед тем, как его можно будет использовать в предложении [copyin](../Topic/copyin.md).  
  
 При компиляции следующего примера возникнет ошибка C3058:  
  
```  
// C3058.cpp // compile with: /openmp int x, y, z; #pragma omp threadprivate(x, z) void test() { #pragma omp parallel copyin(x, y)   // C3058 { } }  
```  
  
 Возможное решение  
  
```  
// C3058b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { } }  
```