---
title: "OMP_DYNAMIC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fcff25541921ccac9dc2e205480dc6277f620b1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
Указывает, может ли OpenMP, время выполнения изменять количество потоков в параллельной области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Примечания  
 `OMP_DYNAMIC` Переменной среды может быть переопределено [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) функции.  
  
 Значение по умолчанию в Visual C++ реализации стандартной OpenMP — `OMP_DYNAMIC=FALSE`.  
  
 Дополнительные сведения см. в разделе [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## <a name="example"></a>Пример  
 Следующая команда задает `OMP_DYNAMIC` переменной среды в значение TRUE:  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 Следующая команда отображает текущее значение параметра `OMP_DYNAMIC` переменной среды:  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)