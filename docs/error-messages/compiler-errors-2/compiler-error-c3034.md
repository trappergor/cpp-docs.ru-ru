---
title: "Ошибка компилятора C3034 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3034"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3034"
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3034
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Директиву OpenMP "директива1" нельзя вложить непосредственно в директиву "директива2"  
  
 Некоторые директивы не могут быть вложенными. Чтобы устранить эту ошибку, можно объединить операторы обеих директив в блок одной директивы или построить последовательные директивы.  
  
 Следующий пример приводит к возникновению ошибки C3034:  
  
```  
// C3034.cpp // compile with: /openmp /link vcomps.lib int main() { #pragma omp single { #pragma omp single   // C3034 { ; } } // Two consecutive single clauses are OK. #pragma omp single { } #pragma omp single { } }  
```