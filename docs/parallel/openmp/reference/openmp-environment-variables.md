---
title: "OpenMP Environment Variables | Microsoft Docs"
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
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Environment Variables
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ссылки на переменные среды, используемые в API модели OpenMP.  
  
 Реализация Visual C\+\+ стандарта OpenMP включает следующие переменные среды.  Эти переменные среды считываются при запуске программы и изменения их значения игнорируются во время выполнения \(например, использование \_putenv\).  
  
|Переменная среды|Описание|  
|----------------------|--------------|  
|[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Определяет, может ли время выполнения OpenMP может обрабатывать количество потоков в параллельной области.|  
|[OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Указывает, включена ли вложенные параллелизм, если вложенные параллелизм не включена, либо заблокирована с `omp_set_nested`.|  
|[OMP\_NUM\_THREADS](../Topic/OMP_NUM_THREADS.md)|Не смогут устанавливать максимальное количество потоков в параллельной области, если не переопределено by [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) OR  [num\_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP\_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Изменяет расширение функциональности [schedule](../../../parallel/openmp/reference/schedule.md) если предложение  `schedule(runtime)` определяет in a  `for` OR  `parallel for` директива.|  
  
## См. также  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)