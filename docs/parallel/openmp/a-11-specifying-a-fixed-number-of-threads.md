---
title: "A.11   Specifying a Fixed Number of Threads | Microsoft Docs"
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
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.11   Specifying a Fixed Number of Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Некоторые программы полагаются на определенном количестве, prespecified потоков для выполнения правильно.  Поскольку реализация\-определен параметр по умолчанию для динамической настройки числа потоков, такие программы могут выбрать для выключения динамическая возможность потоков и явно задать количество потоков для обеспечения переносимости.  В следующем примере показано, как сделать это с помощью `omp_set_dynamic` \([Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39\)и  `omp_set_num_threads` \([Раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице : 36\)  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 В этом примере программа выполняется только в том случае, если она выполняется правильно 16 потока.  Если реализация может не поддерживать 16 потоков, расширение функциональности выполнения данного примера реализация\-определена.  
  
 Обратите внимание, что количество потоков при выполнении параллельной области остается постоянным во время параллельной области, независимо от динамический параметр потоков.  Динамический механизм потоков, указывающее число потоков, используемых в начале параллельной области и сохраняет его постоянным на длительность области.