---
title: 3.1.1 функция omp_set_num_threads | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99c82ff324cbf21612d2459511877d152e2757f5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 Функция omp_set_num_threads
`omp_set_num_threads` Функция задает по умолчанию количество потоков, используемых для последующих параллельных областей, которые задают `num_threads` предложения. Он следующий:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 Значение параметра *num_threads* должно быть положительным целым числом. Его результат зависит от того, включен ли динамическую настройку потоков. Доступен широкий набор правил о взаимодействии между `omp_set_num_threads` функции и динамическую настройку потоков, содержатся в разделе 2.3 на странице 8.  
  
 Эта функция имеет последствия, описанных выше, при вызове из части программы где `omp_in_parallel` функция возвращает ноль. Если он вызывается из части программы где `omp_in_parallel` функция возвращает ненулевое значение, то поведение этой функции не определено.  
  
 Этот вызов имеет приоритет над `OMP_NUM_THREADS` переменной среды. Значение по умолчанию для количества потоков, которые могут быть установлены, вызвав `omp_set_num_threads` или установив `OMP_NUM_THREADS` переменной среды, можно явно переопределить на одном **параллельных** директив, указав `num_threads` предложения.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   `omp_set_dynamic` см. в разделе [раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.  
  
-   `omp_get_dynamic` см. в разделе [раздел 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) на странице 40.  
  
-   `OMP_NUM_THREADS` см. в разделе переменной среды [разделе 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на стр. 48 и разделе 2.3 на странице 8.  
  
-   `num_threads` предложение, в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8