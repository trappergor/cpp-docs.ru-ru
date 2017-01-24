---
title: "Ошибка компилятора C3018 | Microsoft Docs"
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
  - "C3018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3018"
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная1": в проверке или в приращении в операторе For директивы OpenMP должна использоваться переменная индекса "переменная2"  
  
 Цикл `for` в операторе OpenMP должен использовать ту же переменную для проверки и увеличения, которую он использует для индекса.  
  
 При компиляции следующего примера возникнет ошибка C3018:  
  
```  
// C3018.cpp // compile with: /openmp int main() { int i = 0, j = 5; #pragma omp parallel { #pragma omp for for (i = 0; j < 10; ++i)   // C3018 // try the the following line instead // for (i = 0; i < 10; ++i) j *= 2; #pragma omp for for (i = 0; i < 10; j = j + i)   // C3018 // try the the following line instead // for (i = 0; i < 10; i = j + i) j *= 2; } }  
```