---
title: "3.1.3 функция omp_get_max_threads | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e021f0873aa94f53a1218a3278a744a0c7740e65
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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