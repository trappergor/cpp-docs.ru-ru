---
title: "omp_set_num_threads | Microsoft Docs"
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
  - "omp_set_num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_num_threads OpenMP function"
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Устанавливает количество потоков в последующих параллельных областях, если не переопределено a num\_threads предложение.  
  
## Синтаксис  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## Заметки  
 Здесь:  
  
 `num_threads`  
 Количество потоков в параллельной области.  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.1.1 omp\_set\_num\_threads Function](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## Пример  
 См. [omp\_get\_num\_threads](../Topic/omp_get_num_threads.md) пример использования  `omp_set_num_threads`.  
  
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)