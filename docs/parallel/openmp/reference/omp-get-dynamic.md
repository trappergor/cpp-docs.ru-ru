---
title: "omp_get_dynamic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865104055fc98946c09152f328f4812af0120e64
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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