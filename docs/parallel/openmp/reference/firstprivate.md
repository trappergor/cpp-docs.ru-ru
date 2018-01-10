---
title: "firstprivate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: firstprivate
dev_langs: C++
helpviewer_keywords: firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c7d4a5ba23e343f7858bf3320ed05ebce84f1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="firstprivate"></a>firstprivate
Указывает, что каждый поток должен иметь собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`var`|Для переменной экземпляров в каждом потоке, которые инициализируются со значением переменной, так как она существует до параллельной конструкции. Если указано более одной переменной, разделяйте имена переменных запятыми.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="remarks"></a>Примечания  
 `firstprivate`применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Пример  
 Пример использования `firstprivate`, см. пример в [частного](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)