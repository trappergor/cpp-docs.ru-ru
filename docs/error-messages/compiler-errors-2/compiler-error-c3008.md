---
title: "Ошибка компилятора C3008 | Microsoft Docs"
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
  - "C3008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3008"
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"аргумент": в аргументе директивы OpenMP "директива" отсутствует закрывающая скобка "\)"  
  
 Директива OpenMP, которая принимает аргумент, не содержит закрывающую скобку.  
  
 При компиляции следующего примера возникнет ошибка C3008:  
  
```  
// C3008.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x   // C3008 // Try the following line instead: #pragma omp parallel shared(x) { } }  
```