---
title: OMP_NUM_THREADS | Документация Майкрософт
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
ms.openlocfilehash: 39f45b9c81d5339b2b6afe4c77fdc9bac6b5d731
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091170"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
Задает максимальное число потоков в параллельной области, если не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
### <a name="parameters"></a>Параметры
  
*num*<br/>
Максимальное количество потоков в параллельной области, не более 64-разрядная реализация Visual C++.  
  
## <a name="remarks"></a>Примечания  
 **OMP_NUM_THREADS** переменной среды могут быть переопределены [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции или [num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Значение по умолчанию `num` в Visual C++ реализация стандарта OpenMP — это количество виртуальных процессоров, включая процессоры с технологией Hyper-Threading.  
  
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