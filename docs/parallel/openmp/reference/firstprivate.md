---
title: "firstprivate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 03bea93209428a0edbd4c87779d46c633bbe6259
ms.lasthandoff: 02/24/2017

---
# <a name="firstprivate"></a>firstprivate
Указывает, что каждый поток должен иметь свой собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`var`|Для переменной экземпляров в каждом потоке, а инициализируются со значением переменной, так как она существует до параллельной конструкции. Если указано несколько переменных разделяются запятыми имен переменных.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="remarks"></a>Примечания  
 `firstprivate`применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [параллельный](../../../parallel/openmp/reference/parallel.md)  
  
-   [разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [один](../../../parallel/openmp/reference/single.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Пример  
 Пример использования `firstprivate`, см. пример в [частного](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)
