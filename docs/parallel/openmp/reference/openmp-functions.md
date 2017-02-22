---
title: "OpenMP Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Functions
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ссылки на функции, используемые в API модели OpenMP.  
  
 Реализация Visual C\+\+ стандарта OpenMP включает следующие функции.  
  
|Функция|Описание|  
|-------------|--------------|  
|[omp\_destroy\_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Uninitializes блокировка.|  
|[omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Uninitializes nestable блокировка.|  
|[omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Возвращает значение, показывающее, если количество потоков, доступных в последующей может быть параллельной области изменяется во время выполнения.|  
|[omp\_get\_max\_threads](../Topic/omp_get_max_threads.md)|Возвращает целое число, которое равно или больше количество потоков, которые будут доступны, если параллельная область за пределами num\_threads , определенные на этом этапе в коде.|  
|[omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Возвращает значение, указывающее наличие вложенных параллелизм включена.|  
|[omp\_get\_num\_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Возвращает количество процессоров, доступных при вызове функции.|  
|[omp\_get\_num\_threads](../Topic/omp_get_num_threads.md)|Возвращает количество потоков в параллельной области.|  
|[omp\_get\_thread\_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Возвращает число потоков потока выполнения в его команда потока.|  
|[omp\_get\_wtick](../Topic/omp_get_wtick.md)|Возвращает количество секунд между тактами часов процессора.|  
|[omp\_get\_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Возвращает значение времени в секундах истекл от какого\-либо точки.|  
|[omp\_in\_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Возвращает ненулевое если вызывается из параллельной области.|  
|[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Инициализирует простая блокировка.|  
|[omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md)|Инициализирует блокировка.|  
|[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Указывает количество потоков, доступных в последующей может быть параллельной области изменяется во время выполнения.|  
|[omp\_set\_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Блоки поток выполнения до тех пор, пока блокировка не будет доступна.|  
|[omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Блоки поток выполнения до тех пор, пока блокировка не будет доступна.|  
|[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Разрешает вложенные параллелизм.|  
|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Устанавливает количество потоков в последующих параллельных областях, если не переопределено a num\_threads предложение.|  
|[omp\_test\_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Попытки установить блокировку, но не блокируют выполнение потока.|  
|[omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Пытается перевести nestable блокировки, но не блокируют выполнение потока.|  
|[omp\_unset\_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Выпуски блокировка.|  
|[omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Выпуски nestable блокировка.|  
  
## См. также  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)