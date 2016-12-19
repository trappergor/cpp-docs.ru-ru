---
title: "3.1.2 omp_get_num_threads Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.2 omp_get_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Omp\_get\_num\_threads функция возвращает число потоков в данный момент в команде при выполнении параллельной области, из которой он вызывается.  Формат следующий:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **num\_threads** предложение  **omp\_set\_num\_threads** функция and  **OMP\_NUM\_THREADS** управление переменной среды количество потоков в рабочей группе.  
  
 Если число потоков явно не задано пользователем, то значение по умолчанию реализация\-определено.  Эта функция обеспечивает привязку к ближайший заключать **Параллельно** директива.  Если вызывается с серийной части программы, либо из вложенного параллельной области, сериализовать эта функция возвращает значение 1.  
  
## Перекрестные ссылки:  
  
-   **OMP\_NUM\_THREADS** переменная среды выполнения, см. в разделе  [Раздел 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на странице 48.  
  
-   **num\_threads** предложение см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **Параллельно** конструкция см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.