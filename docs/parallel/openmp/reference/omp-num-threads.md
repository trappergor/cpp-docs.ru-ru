---
title: "OMP_NUM_THREADS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9fc343fd41bf0661099aee2cb4f890a215a64fed
ms.lasthandoff: 02/24/2017

---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
Задает максимальное число потоков в параллельной области, если они не переопределены [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `num`  
 Максимальное число потоков в параллельной области, до 64 в реализации Visual C++.  
  
## <a name="remarks"></a>Примечания  
 **OMP_NUM_THREADS** переменной среды могут быть переопределены [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Значение по умолчанию `num` в Visual C++ реализация стандарта OpenMP — количество виртуальных процессоров, включая процессоры с технологией Hyper-Threading.  
  
 Дополнительные сведения см. в разделе [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Пример  
 Следующая команда задает **OMP_NUM_THREADS** переменной среды до 16:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Следующая команда отображает текущее значение **OMP_NUM_THREADS** переменной среды:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)
