---
title: "4.2 OMP_NUM_THREADS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c2b766d0e3be9b4f1d272a6e3fa205cfcb87039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
**OMP_NUM_THREADS** переменной среды задает по умолчанию количество потоков, используемых во время выполнения, если это количество явно изменен путем вызова **omp_set_num_threads** библиотечная процедура или явный **num_threads** предложение на **параллельных** директивы.  
  
 Значение **OMP_NUM_THREADS** переменной среды должно быть положительным целым числом. Его результат зависит от того, включен ли динамическую настройку потоков. Доступен широкий набор правил о взаимодействии между **OMP_NUM_THREADS** среды переменных и динамические корректировки потоков, содержатся в разделе 2.3 на странице 8.  
  
 Если не указано значение для **OMP_NUM_THREADS** переменной среды, или если значение не является положительным целым числом или если значение превышает максимальное число потоков система может поддерживать, число потоков, используемых определяется реализацией.  
  
 Пример  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **num_threads** предложение, в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **omp_set_num_threads** см. в разделе [раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на стр.  
  
-   **omp_set_dynamic** см. в разделе [раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.