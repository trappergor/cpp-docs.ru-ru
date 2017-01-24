---
title: "3.1.3 omp_get_max_threads Function | Microsoft Docs"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.3 omp_get_max_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**omp\_get\_max\_threads** функция возвращает целое число, которое гарантирует, что хотя бы как большим, как количество потоков, которые используются для формирования команды при параллельной области без a  **num\_threads** предложение было быть столкнутым на этом этапе в коде.  Формат следующий:  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Следующее express нижнюю границу на значении omp\_get\_max\_threads.  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Обратите внимание, что если последующая параллельной области использует **num\_threads** предложение, чтобы запросить определенное количество потоков, гарантии на нижней границы результата  **omp\_get\_max\_threads** не существует длинное не содержит.  
  
 Omp\_get\_max\_threads возвращаемое значение функции могут быть использованы для динамического выбора наличии соответствующего места для всех потоков в рабочей группе сформированной в последующей параллельной области.  
  
## Перекрестные ссылки:  
  
-   **omp\_get\_num\_threads** функция см. в разделе  [Раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на странице 37.  
  
-   **omp\_set\_num\_threads** функция см. в разделе  [Раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице 36.  
  
-   **omp\_set\_dynamic** функция см. в разделе  [Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.  
  
-   **num\_threads** предложение см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.