---
title: "num_threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_threads OpenMP clause"
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Устанавливает количество потоков в рабочей группе потока.  
  
## Синтаксис  
  
```  
num_threads(num)  
```  
  
## Заметки  
 Здесь:  
  
 `num`  
 Число потоков  
  
## Заметки  
 `num_threads` предложение имеет ту же функциональность, что и  [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функция.  
  
 `num_threads` применяется к следующим рекомендациям:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Пример  
 См. [parallel](../../../parallel/openmp/reference/parallel.md) пример использования  `num_threads` предложение.  
  
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)