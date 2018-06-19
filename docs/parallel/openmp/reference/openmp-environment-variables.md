---
title: Переменные среды OpenMP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02248b7725f2a4312f26984c798e7248463d2615
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692312"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP
Ссылки на переменные среды, используемые в OpenMP API.  
  
 Реализация Visual C++ OpenMP standard включает следующие переменные среды. Эти переменные среды считываются при запуске программы и изменения их значения учитываются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|переменная среды;|Описание|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Указывает, может ли OpenMP, время выполнения изменять количество потоков в параллельной области.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Указывает, будет ли вложенный параллелизм, если не включена или отключена с вложенной параллелизма `omp_set_nested`.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Задает максимальное число потоков в параллельной области, если иное не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Изменяет поведение [расписания](../../../parallel/openmp/reference/schedule.md) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директивы.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)