---
title: OMP_NUM_THREADS | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e25369f18f542198638e324110ba14d10b8ddc69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691772"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
Задает максимальное число потоков в параллельной области, если иное не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `num`  
 Максимальное число потоков в параллельной области, не более 64 реализации в Visual C++.  
  
## <a name="remarks"></a>Примечания  
 **OMP_NUM_THREADS** переменной среды может быть переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Значение по умолчанию `num` в Visual C++ реализацию стандарта OpenMP — количество виртуальных процессоров, включая ЦП Hyper-Threading.  
  
 Дополнительные сведения см. в разделе [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Пример  
 Следующая команда задает **OMP_NUM_THREADS** переменной среды до 16:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Следующая команда отображает текущее значение параметра **OMP_NUM_THREADS** переменной среды:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)