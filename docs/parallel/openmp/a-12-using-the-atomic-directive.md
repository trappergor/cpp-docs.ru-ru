---
title: "A.12   Using the atomic Directive | Microsoft Docs"
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
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.12   Using the atomic Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В следующем примере избежать состояния гонки \(синхронные обновления элемента x несколькими потоками\) с помощью `atomic` директива \([Раздел 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) на странице : 19\)  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 Преимущество использования `atomic` директива в этом примере, что он допускает обновления 2 различных элементов x, чтобы выполняться параллельно.  Если набор узлов a `critical` директива \([Раздел 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) на странице 18\) использовать вместо, тогда все обновления к элементам x выполнять последовательно \(но не гарантированном в любом порядке\).  
  
 Обратите внимание, что `atomic` директива применяется только к выписке c или C\+\+ непосредственно после него.  В результате элементы *y* обновление атомарным образом в этом примере.