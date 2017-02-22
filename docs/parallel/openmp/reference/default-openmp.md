---
title: "default (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default OpenMP clause"
  - "defaults, OpenMP clause"
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# default (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет расширение функциональности unscoped переменных в параллельной области.  
  
## Синтаксис  
  
```  
default(shared | none)  
```  
  
## Заметки  
 `shared`в результате, если  `default` предложение не указано, не означает, что любая переменная обрабатывается в параллельной области если было задано off  [shared](../../../parallel/openmp/reference/shared-openmp.md) предложение.  `none` означает, что все переменные, используемые в параллельной области, которые выполняются с  [private](../../../parallel/openmp/reference/private-openmp.md)"  [shared](../../../parallel/openmp/reference/shared-openmp.md)"  [reduction](../../../parallel/openmp/reference/reduction.md)"  [firstprivate](../Topic/firstprivate.md)или  [lastprivate](../../../parallel/openmp/reference/lastprivate.md) предложения вызовет ошибку компилятора.  
  
 `default` применяется к следующим рекомендациям:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md).  
  
## Пример  
 См. [private](../../../parallel/openmp/reference/private-openmp.md) пример использования  `default`.  
  
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)