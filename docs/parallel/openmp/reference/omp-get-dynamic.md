---
title: "omp_get_dynamic | Microsoft Docs"
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
  - "omp_get_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_dynamic OpenMP function"
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Возвращает значение, показывающее, если количество потоков, доступных в последующей может быть параллельной области изменяется во время выполнения.  
  
## Синтаксис  
  
```  
int omp_get_dynamic();  
```  
  
## Возвращаемое значение  
 Если значение ненулевое, динамическую настройку потоков включена.  
  
## Заметки  
 Динамическая корректировка потоков, указанной с помощью [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) и  [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Дополнительные сведения см. в разделе [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Пример  
 См. [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) пример использования  `omp_get_dynamic`.  
  
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)