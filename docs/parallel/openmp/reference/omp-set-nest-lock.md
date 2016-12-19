---
title: "omp_set_nest_lock | Microsoft Docs"
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
  - "omp_set_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nest_lock OpenMP function"
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блоки поток выполнения до тех пор, пока блокировка не будет доступна.  
  
## Синтаксис  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## Заметки  
 Здесь:  
  
 `lock`  
 Переменная типа [omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md) это был инициализирован с  [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md).  
  
## Заметки  
 Дополнительные сведения см. в разделе [3.2.3 omp\_set\_lock and omp\_set\_nest\_lock Functions](../Topic/3.2.3%20omp_set_lock%20and%20omp_set_nest_lock%20Functions.md).  
  
## Примеры  
 См. [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) пример использования  `omp_set_nest_lock`.  
  
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)