---
title: "A.6   Using the lastprivate Clause | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.6   Using the lastprivate Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Правильные зависит от выполнения иногда значение, более поздней итерации цикла присвоенный переменной.  Такие программы должен перечислить все такие переменные в качестве аргументов a `lastprivate` предложение \([Раздел 2.7.2.3](../Topic/2.7.2.3%20lastprivate.md) на странице 27\) таким образом, что значения переменных будут такими же, как если цикл будет выполняться последовательно.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 В предыдущем примере значение `i` в конце параллельной области приравняет  `n–1`в последовательном случае.