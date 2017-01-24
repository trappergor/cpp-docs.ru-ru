---
title: "shared (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared OpenMP clause"
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# shared (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, что одну или несколько переменных должны быть разделены среди всех потоков.  
  
## Синтаксис  
  
```  
shared(var)  
```  
  
## Заметки  
 Здесь:  
  
 `var`  
 Одно более несколько переменных для совместного использования.  Если более чем одна переменная задана, то отдельные имена переменных с запятой.  
  
## Заметки  
 Другой способ совместного использования переменных между потоками с copyprivate предложение.  
  
 `shared` применяется к следующим рекомендациям:  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.4 shared](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## Пример  
 См. [private](../../../parallel/openmp/reference/private-openmp.md) пример использования  `shared`.  
  
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)