---
title: "omp_set_dynamic | Microsoft Docs"
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
  - "omp_set_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_dynamic OpenMP function"
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает количество потоков, доступных в последующей может быть параллельной области изменяется во время выполнения.  
  
## Синтаксис  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## Заметки  
 Здесь:  
  
 `val`  
 Значение, указывающее, является ли число потоков, доступных в последующей может быть параллельной области изменяется с помощью среды выполнения рабочего процесса.  Если значение ненулевое, среда выполнения может обрабатывать количество потоков, если значение равно нулю, среда выполнения не будет обрабатывать динамически количество потоков.  
  
## Заметки  
 Число потоков не превысит заданное значение by [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или by  [OMP\_NUM\_THREADS](../Topic/OMP_NUM_THREADS.md).  
  
 Используйте [omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) отобразить текущий параметр  `omp_set_dynamic`.  
  
 Параметр `omp_set_dynamic` переопределяет параметр  [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) переменная среды.  
  
 Дополнительные сведения см. в разделе [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Пример  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
  **1**  
**1**   
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)