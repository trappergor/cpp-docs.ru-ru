---
title: "omp_test_lock | Microsoft Docs"
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
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Попытки установить блокировку, но не блокируют выполнение потока.  
  
## Синтаксис  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## Заметки  
 Здесь:  
  
 `lock`  
 Переменная типа [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) это был инициализирован с  [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../Topic/3.2.5%20omp_test_lock%20and%20omp_test_nest_lock%20Functions.md).  
  
## Пример  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **Поток 1 \- приобретенное simple\_lock**  
**Поток 1 \- освобожданное simple\_lock**  
**Поток 0 \- " не удалось получить simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 0 \- " не удалось получить simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 2 \- приобретенное simple\_lock**  
**Поток 0 \- " не удалось получить simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 0 \- " не удалось получить simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 2 \- освобожданное simple\_lock**  
**Поток 0 \- " не удалось получить simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 0 \- приобретенное simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 0 \- освобожданное simple\_lock**  
**Поток 3 \- " не удалось получить simple\_lock**  
**Поток 3 \- приобретенное simple\_lock**  
**Поток 3 \- освобожданное simple\_lock**   
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)