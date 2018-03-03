---
title: "3.1.4 функция omp_get_thread_num | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b968d103631dafcdd2132cb749ae8feed30085
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 Функция omp_get_thread_num
`omp_get_thread_num` Функция возвращает номер потока, в его команде потока, выполняющего функции. Поток номеров лежит между 0 и **omp_get_num_threads()**-1, включительно. Главный поток команды является потоком 0.  
  
 Он следующий:  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 При вызове из последовательного области `omp_get_thread_num` возвращает 0. Если вызывается внутри параллельной области вложенного, который сериализуется, эта функция возвращает 0.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   `omp_get_num_threads`см. в разделе [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на странице 37.