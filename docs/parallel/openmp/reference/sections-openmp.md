---
title: "sections (OpenMP) | Microsoft Docs"
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
  - "section"
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sections OpenMP directive"
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sections (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет разделы кода, который должен быть секционированы среди всех потоков.  
  
## Синтаксис  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## Заметки  
 Здесь:  
  
 `clause` \(необязательный параметр\)  
 Ноль или несколько предложений.  Эти раздел " примечания " список предложений, поддерживаемых by **Разделы**.  
  
## Заметки  
 **Разделы** директива может содержать ноль или более  **раздел** директивы.  
  
 **Разделы** директива поддерживает следующие предложений OpenMP.  
  
-   [firstprivate](../Topic/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 If **Параллельно** определяет также,  `clause` может быть любым предложением выполнения  **Параллельно** OR  **Разделы** директивы, кроме  `nowait`.  
  
 Дополнительные сведения см. в разделе [2.4.2 sections Construct](../../../parallel/openmp/2-4-2-sections-construct.md).  
  
## Пример  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
  **Hello из потока 0**  
**Hello из потока 0**   
## См. также  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)