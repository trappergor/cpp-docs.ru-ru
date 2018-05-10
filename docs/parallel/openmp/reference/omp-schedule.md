---
title: OMP_SCHEDULE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5052aaadc673e38a844ea5b0d1e11ff3a96f3fbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Изменяет поведение [расписания](../../../parallel/openmp/reference/schedule.md) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директивы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `size` (необязательно)  
 Указывает размер итераций. `size` Должно быть положительным целым числом. Значение по умолчанию — 1, за исключением случаев `type` является статическим. Если не является допустимым `type` — `runtime`.  
  
 `type`  
 Тип расписания:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Примечания  
 Значение по умолчанию в Visual C++ реализации стандартной OpenMP — `OMP_SCHEDULE=static,0`.  
  
 Дополнительные сведения см. в разделе [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## <a name="example"></a>Пример  
 Следующая команда задает **OMP_SCHEDULE** переменной среды:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Следующая команда отображает текущее значение параметра **OMP_SCHEDULE** переменной среды:  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)