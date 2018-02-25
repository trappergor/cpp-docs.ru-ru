---
title: "omp_get_nested | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df6a3fafdb749031ae5e55a58e1e26ccad76985c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnested"></a>omp_get_nested
Возвращает значение, указывающее, включено ли вложенный параллелизм.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, вложенный параллелизм включен.  
  
## <a name="remarks"></a>Примечания  
 Вложенный параллелизм, указанном с помощью [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) и [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 Дополнительные сведения см. в разделе [3.1.10 функция omp_get_nested](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## <a name="example"></a>Пример  
 В разделе [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) пример использования `omp_get_nested`.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)