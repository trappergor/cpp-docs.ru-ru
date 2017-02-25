---
title: "omp_destroy_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_destroy_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_destroy_lock OpenMP function"
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# omp_destroy_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Uninitializes блокировка.  
  
## Синтаксис  
  
```  
void omp_destroy_lock(  
   omp_lock_t *lock  
);  
```  
  
## Заметки  
 Здесь:  
  
 `lock`  
 Переменная типа [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) это был инициализирован с  [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.2.2 omp\_destroy\_lock and omp\_destroy\_nest\_lock Functions](../Topic/3.2.2%20omp_destroy_lock%20and%20omp_destroy_nest_lock%20Functions.md).  
  
## Пример  
 См. [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) пример использования  `omp_destroy_lock`.  
  
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)