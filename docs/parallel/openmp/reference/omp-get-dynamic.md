---
title: omp_get_dynamic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d97cae8091f88c283412b36ef757b03c72f7580d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
Возвращает значение, указывающее, если число потоков, доступных в последующих параллельной области может настраиваться по времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, динамическую настройку потоков включен.  
  
## <a name="remarks"></a>Примечания  
 Указано динамическую настройку потоков с [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) и [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Пример  
 В разделе [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) пример использования `omp_get_dynamic`.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)