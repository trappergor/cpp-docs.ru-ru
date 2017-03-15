---
title: "3.1.4 omp_get_thread_num Function | Microsoft Docs"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.4 omp_get_thread_num Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_thread_num` функция возвращает число потоков, в его workgroup потока при выполнении функции.  Число потоков находится между 0 и **omp\_get\_num\_threads \(\)**\- 1 включительно.  Главный поток команды поток 0.  
  
 Формат следующий:  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 Если вызывается из области, то серийной `omp_get_thread_num` возвращает 0.  Если вызывается из вложенных параллельной области, сериализуется, функция возвращает 0.  
  
## Перекрестные ссылки:  
  
-   `omp_get_num_threads` функция см. в разделе  [Раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на странице 37.