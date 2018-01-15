---
title: "3.1.9 функция omp_set_nested | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0910e7df0ebd423b9967fd0eb7931b7434ba94fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="319-ompsetnested-function"></a>3.1.9 Функция omp_set_nested
**Omp_set_nested** функция включает или отключает вложенный параллелизм. Он следующий:  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Если *вложенных* равен 0, вложенные параллелизм отключен, используемого по умолчанию и вложенные области параллельных сериализуются и выполнения текущего потока. Если *вложенных* вычисляет задано ненулевое значение, включен вложенный параллелизм и развертывание дополнительных потоков для формирования вложенных групп может параллельной области, которые являются вложенными.  
  
 Эта функция имеет последствия, описанных выше, при вызове из части программы где **omp_in_parallel** функция возвращает ноль. Если он вызывается из части программы где **omp_in_parallel** функция возвращает ненулевое значение, то поведение этой функции не определено.  
  
 Этот вызов имеет приоритет над **OMP_NESTED** переменной среды.  
  
 При включении вложенного параллелизма количество потоков, используемых для выполнения вложенных параллельных областей определяется реализацией. В результате реализации OpenMP совместимые разрешены для сериализации вложенные параллельной области, даже в том случае, если включена вложенный параллелизм.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **OMP_NESTED** переменной, см. в разделе среды [раздел 4.4](../../parallel/openmp/4-4-omp-nested.md) на стр.  
  
-   **omp_in_parallel** см. в разделе [раздел 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) на странице 38.