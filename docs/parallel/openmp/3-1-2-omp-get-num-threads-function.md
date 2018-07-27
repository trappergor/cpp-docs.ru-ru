---
title: 3.1.2 функция omp_get_num_threads | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df01d571b67ff6d252d85128fcc8c1d26a6e94a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687443"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 Функция omp_get_num_threads
**Omp_get_num_threads** функция возвращает число потоков в настоящее время в выполнении параллельной области, из которой вызывается команда. Он следующий:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num_threads** предложение, **omp_set_num_threads** функции и **OMP_NUM_THREADS** переменной среды управлять количеством потоков в команде.  
  
 Если число потоков, не было явно задано пользователем, значение по умолчанию определяется реализацией. Эта функция привязывается к ближайшей окружению **параллельных** директивы. Если вызывается из последовательного части программы или из вложенных параллельной области, в который сериализуется, эта функция возвращает значение 1.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **OMP_NUM_THREADS** переменной, см. в разделе среды [разделе 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на стр. 48.  
  
-   **num_threads** предложение, в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **Параллельные** создания см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.