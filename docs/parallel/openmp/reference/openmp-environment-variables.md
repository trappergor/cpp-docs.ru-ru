---
title: "Переменные среды OpenMP | Документы Microsoft"
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
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7e0089399cd1a6d91a1324d8c986ea22c1fae63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP
Ссылки на переменные среды, используемые в OpenMP API.  
  
 Реализация Visual C++ OpenMP standard включает следующие переменные среды. Эти переменные среды считываются при запуске программы и изменения их значения учитываются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|переменная среды;|Описание:|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Указывает, может ли OpenMP, время выполнения изменять количество потоков в параллельной области.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Указывает, будет ли вложенный параллелизм, если не включена или отключена с вложенной параллелизма `omp_set_nested`.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Задает максимальное число потоков в параллельной области, если иное не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Изменяет поведение [расписания](../../../parallel/openmp/reference/schedule.md) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директивы.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)