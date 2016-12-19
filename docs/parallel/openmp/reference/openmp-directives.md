---
title: "OpenMP Directives | Microsoft Docs"
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
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Directives
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Предоставляет ссылки на инструкции, используемые в API модели OpenMP.  
  
 Visual C\+\+ поддерживает следующие директивы OpenMP.  
  
|Директива|Описание|  
|---------------|--------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Указывает, что ячейки памяти, который будет обновлен атомарным образом.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Синхронизировать все потоки в рабочей группе; все потоки приостановят в барьере, до тех пор, пока все потоки не будут выполняться барьера.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Указывает, что только код выполняется в одном потоке одновременно.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Указывает, что все потоки имеют одинаковое представление в памяти для всех общих объектов.|  
|[for](../Topic/for%20\(OpenMP\).md)|Вызывает завершивший работу в цикл for, в параллельной области, разбиваемый между потоками.|  
|[master](../../../parallel/openmp/reference/master.md)|Указывает, что только главное threadshould выполняет шаг программы.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Указывает, что код под параллелизированное for должен быть выполнен как последовательный цикл.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Определяет параллельной области, которая код, который будет выполнен несколькими потоками одновременно.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|Определяет разделы кода, который должен быть секционированы среди всех потоков.|  
|[single](../Topic/single.md)|Позволяет указать, что фрагмент кода должен выполняться в одном потоке, не обязательно главный поток.|  
|[threadprivate](../Topic/threadprivate.md)|Указывает, что переменная является закрытой в поток.|  
  
## См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)