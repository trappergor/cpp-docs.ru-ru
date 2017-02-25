---
title: "barrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barrier OpenMP directive"
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# barrier
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Синхронизировать все потоки в рабочей группе; все потоки приостановят в барьере, до тех пор, пока все потоки не будут выполняться барьера.  
  
## Синтаксис  
  
```  
#pragma omp barrier  
```  
  
## Заметки  
 `barrier` директива не поддерживает никаких предложений OpenMP.  
  
 Дополнительные сведения см. в разделе [2.6.3 barrier Directive](../../../parallel/openmp/2-6-3-barrier-directive.md).  
  
## Пример  
 Пример использования `barrier`см.  [master](../../../parallel/openmp/reference/master.md).  
  
## См. также  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)