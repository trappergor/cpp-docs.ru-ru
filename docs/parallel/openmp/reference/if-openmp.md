---
title: "if (OpenMP) | Microsoft Docs"
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
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "if OpenMP clause"
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, должен ли быть выполнен в режиме параллельного цикла или последовательно.  
  
## Синтаксис  
  
```  
if(expression)  
```  
  
## Заметки  
 Здесь:  
  
 `expression`  
 Объединенный выражение, если оно имеет значение true \(\) не равен нулю, приводит к тому, что код в параллельной области выполняться параллельно.  Если выражение имеет значение false \(нуля\), то параллельная область последовательно выполняется одним потоком \(\).  
  
## Заметки  
 `if` применяется к следующим рекомендациям:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Пример  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
  **val \= 0, при сериализации**  
**val \= 2, 2 параллелизировано с потоками**   
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)