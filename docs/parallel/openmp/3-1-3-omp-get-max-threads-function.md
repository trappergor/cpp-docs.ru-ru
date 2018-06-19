---
title: 3.1.3 функция omp_get_max_threads | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2afa797cc74a50041f2ea24f76fa07ffe109072b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687515"
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 Функция omp_get_max_threads
**Omp_get_max_threads** функция возвращает целое число, которое гарантированно будет по крайней мере число потоков, которые используются для формирования команды при параллельной области без **num_threads** предложения бы быть обнаружены в этой точке в коде. Он следующий:  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Следующие выражает нижняя граница диапазона на значении **omp_get_max_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Обратите внимание, что если последующие параллельной области использует **num_threads** предложений, чтобы запросить определенное число потоков, гарантии на нижней границей, равной результат **omp_get_max_threads** не содержит много.  
  
 **Omp_get_max_threads** возвращаемое значение функции можно использовать для динамического выделения достаточно дискового пространства для всех потоков в формирование в последующих параллельной области группы.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **omp_get_num_threads** см. в разделе [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на странице 37.  
  
-   **omp_set_num_threads** см. в разделе [раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на стр.  
  
-   **omp_set_dynamic** см. в разделе [раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.  
  
-   **num_threads** предложение, в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.