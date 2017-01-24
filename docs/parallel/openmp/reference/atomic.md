---
title: "atomic | Microsoft Docs"
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
  - "atomic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atomic OpenMP directive"
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# atomic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, что ячейки памяти, который будет обновлен атомарным образом.  
  
## Синтаксис  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### Параметры  
 `expression`  
 Выписка, содержащий ячейки памяти lvalue которой необходимо защититься от нескольких записей.  Дополнительные сведения о формах недопустимым выражений см. в разделе спецификация по OpenMP.  
  
## Заметки  
 `atomic` директива не поддерживает никаких предложений OpenMP.  
  
 Дополнительные сведения см. в разделе [2.6.4 atomic Construct](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## Пример  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
  **Число потоков. 10**   
## См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)