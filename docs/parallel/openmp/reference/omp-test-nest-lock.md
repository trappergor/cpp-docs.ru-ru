---
title: "omp_test_nest_lock | Microsoft Docs"
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
  - "omp_test_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_nest_lock OpenMP function"
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Пытается перевести nestable блокировки, но не блокируют выполнение потока.  
  
## Синтаксис  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## Заметки  
 Здесь:  
  
 `lock`  
 Переменная типа [omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md) это был инициализирован с  [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md).  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../Topic/3.2.5%20omp_test_lock%20and%20omp_test_nest_lock%20Functions.md).  
  
## Пример  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
  **Поток 1 \- приобретенное nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**1 \- Приобретенное поток снова nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**Поток 1 \- освобожданное nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**Поток 1 \- освобожданное nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**Поток 3 \- приобретенное nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**3 \- Приобретенное поток снова nestable\_lock**  
**Поток 0 \- " не удалось получить nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 3 \- освобожданное nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 3 \- освобожданное nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 0 \- приобретенное nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**0 \- Приобретенное поток снова nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 0 \- освобожданное nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 0 \- освобожданное nestable\_lock**  
**Поток 2 \- " не удалось получить nestable\_lock**  
**Поток 2 \- приобретенное nestable\_lock**  
**2 \- Приобретенное поток снова nestable\_lock**  
**Поток 2 \- освобожданное nestable\_lock**  
**Поток 2 \- освобожданное nestable\_lock**   
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)