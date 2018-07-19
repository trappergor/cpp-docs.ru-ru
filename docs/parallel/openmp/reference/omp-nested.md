---
title: OMP_NESTED | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6b51df88ae700f81cf84250cc06ae24c9131fec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691226"
---
# <a name="ompnested"></a>OMP_NESTED
Указывает, будет ли вложенный параллелизм, если не включена или отключена с вложенной параллелизма `omp_set_nested`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Примечания  
 `OMP_NESTED` Переменной среды может быть переопределено [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) функции.  
  
 Значение по умолчанию в Visual C++ реализации стандартной OpenMP — `OMP_DYNAMIC=FALSE`.  
  
 Дополнительные сведения см. в разделе [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).  
  
## <a name="example"></a>Пример  
 Следующая команда задает `OMP_NESTED` переменной среды в значение TRUE:  
  
```  
set OMP_NESTED=TRUE  
```  
  
 Следующая команда отображает текущее значение параметра `OMP_NESTED` переменной среды:  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)