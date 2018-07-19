---
title: OMP_DYNAMIC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de4a81d861bf72943a67356577da37c36df63f69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695815"
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