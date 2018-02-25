---
title: "Функции OpenMP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1578adbd0689e6f011ce52266c4d8e0eef9947b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-functions"></a>Функции OpenMP
Ссылки на функции, используемые в OpenMP API.  
  
 Реализация Visual C++ OpenMP standard включает следующие функции.  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Отменяет инициализацию блокировки.|  
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Отменяет инициализацию которая блокировки.|  
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Возвращает значение, указывающее, если число потоков, доступных в последующих параллельной области может настраиваться по времени выполнения.|  
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Возвращает целое число, равное или больше, чем число потоков, которые были бы доступны, если параллельной области без [num_threads](../../../parallel/openmp/reference/num-threads.md) были определены в этой точке в коде.|  
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Возвращает значение, указывающее, включено ли вложенный параллелизм.|  
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Возвращает количество процессоров, доступных при вызове функции.|  
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Возвращает число потоков в параллельной области.|  
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Возвращает количество потоков потока, выполняющегося в его команде потока.|  
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|Возвращает количество секунд между тактов процессора.|  
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Возвращает значение в секундах времени, прошедшего с какой-то момент.|  
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Возвращает ненулевое значение, если вызвана внутри параллельной области.|  
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Инициализирует простые блокировки.|  
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Инициализирует блокировки.|  
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Указывает, что число потоков, доступных в последующих параллельной области может настраиваться по времени выполнения.|  
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Блоки потоков выполнения, пока блокировка не освободится.|  
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Блоки потоков выполнения, пока блокировка не освободится.|  
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Включает вложенные параллелизма.|  
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Задает число потоков в последующих параллельных регионах, если иное не переопределено [num_threads](../../../parallel/openmp/reference/num-threads.md) предложения.|  
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Пытается установить блокировку, но не блокирует выполнение потока.|  
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Пытается установить блокировку, которая, но не блокирует выполнение потока.|  
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Освобождает блокировку.|  
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Освобождение блокировки, которая.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)