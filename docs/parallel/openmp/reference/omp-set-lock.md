---
title: "omp_set_lock | Microsoft Docs"
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
  - "omp_set_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_lock OpenMP function"
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блоки поток выполнения до тех пор, пока блокировка не будет доступна.  
  
## Синтаксис  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
## Заметки  
 Здесь:  
  
 `lock`  
 Переменная типа [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) это был инициализирован с  [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.2.3 omp\_set\_lock and omp\_set\_nest\_lock Functions](../Topic/3.2.3%20omp_set_lock%20and%20omp_set_nest_lock%20Functions.md).  
  
## Примеры  
 См. [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) пример использования  `omp_set_lock`.  
  
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)