---
title: "parallel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel OpenMP directive"
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет параллельной области, которая код, который будет выполнен несколькими потоками одновременно.  
  
## Синтаксис  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## Заметки  
 Здесь:  
  
 `clause` \(необязательный параметр\)  
 Ноль или несколько предложений.  Эти раздел " примечания " список предложений, поддерживаемых by **Параллельно**.  
  
## Заметки  
 **Параллельно** директива поддерживает следующие предложений OpenMP.  
  
-   [copyin](../Topic/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../Topic/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num\_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Параллельно** может также использоваться с  [sections](../../../parallel/openmp/reference/sections-openmp.md) и  [for](../Topic/for%20\(OpenMP\).md) директивы.  
  
 Дополнительные сведения см. в разделе [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Пример  
 В следующем образце показано, как задать число потоков и определить параллельной области.  По умолчанию количество потоков равно количество логических процессоров в компьютере.  Например, если имеется физический компьютер с одним процессором, включен hyperthreading, он будет иметь 2 логических процессоров и 2 потоков.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
  **Hello из потока 0**  
**Hello из потока 1**  
**Hello из потока 2**  
**Hello из потока 3**   
## Комментарий  
 Видит, что порядок вывода могут различаться на разных компьютерах.  
  
## См. также  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)