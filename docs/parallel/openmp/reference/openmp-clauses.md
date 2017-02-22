---
title: "OpenMP Clauses | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Clauses
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ссылки на выражения, используемые в API модели OpenMP.  
  
 Visual C\+\+ поддерживает следующие предложений OpenMP.  
  
|Предложение|Описание|  
|-----------------|--------------|  
|[copyin](../Topic/copyin.md)|Позволяет потокам доступа к значению главного потока, a [threadprivate](../Topic/threadprivate.md) переменную.|  
|[copyprivate](../Topic/copyprivate.md)|Указывает, что одну или несколько переменных должны быть разделены среди всех потоков.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|Определяет расширение функциональности unscoped переменных в параллельной области.|  
|[firstprivate](../Topic/firstprivate.md)|Указывает, что каждый поток должен иметь собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, поскольку она существует, перед параллельной конструкции.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|Указывает, должен ли быть выполнен в режиме параллельного цикла или последовательно.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Указывает, что версия включающего контекста переменной задается равным закрытой версии любого поток выполняет итерацию \(последняя конструкция для\-цикла\) или последний раздел \#pragma \(partitions\).|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Переопределяет барьера неявный в директиве.|  
|[num\_threads](../../../parallel/openmp/reference/num-threads.md)|Устанавливает количество потоков в рабочей группе потока.|  
|[ordered](../Topic/ordered%20\(OpenMP%20Clauses\).md)|Требуется в параллельном режиме [for](../Topic/for%20\(OpenMP\).md) если оператор  [ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md) директива, которая будет использоваться в цикле.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|Указывает, что каждый поток должен иметь собственный экземпляр переменной.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|Указывает, что одну или несколько переменных, которые являются закрытыми к каждому потоку в операции уменьшения в конце параллельной области.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|Применяется к [for](../Topic/for%20\(OpenMP\).md) директива.|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|Указывает, что одну или несколько переменных должны быть разделены среди всех потоков.|  
  
## См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)