---
title: "OMP_SCHEDULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_SCHEDULE
dev_langs: C++
helpviewer_keywords: OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c29ec07f9a912fb66adc391465885da8030cc466
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
 Указывает размер итераций. `size`должно быть положительным целым числом. Значение по умолчанию — 1, за исключением случаев `type` является статическим. Если не является допустимым `type` — `runtime`.  
  
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