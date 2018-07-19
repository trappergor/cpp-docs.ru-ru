---
title: firstprivate | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10b5a270feb638a98c060b58e90af8146ff97325
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691707"
---
# <a name="firstprivate"></a>firstprivate
Указывает, что каждый поток должен иметь собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`var`|Для переменной экземпляров в каждом потоке, которые инициализируются со значением переменной, так как она существует до параллельной конструкции. Если указано более одной переменной, разделяйте имена переменных запятыми.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="remarks"></a>Примечания  
 `firstprivate` применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Пример  
 Пример использования `firstprivate`, см. пример в [частного](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)