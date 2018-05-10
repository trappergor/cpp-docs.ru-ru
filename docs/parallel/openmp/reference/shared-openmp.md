---
title: Общие (OpenMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8287f96f80748272e29b22ed5c43c364f4353b86
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="shared-openmp"></a>shared (OpenMP)
Указывает, что один или несколько переменных должны совместно используются всеми потоками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Один для получения дополнительных переменные для совместного использования. Если указано более одной переменной, разделяйте имена переменных запятыми.  
  
## <a name="remarks"></a>Примечания  
 Другой способ совместного использования переменных потоков — с [copyprivate](../../../parallel/openmp/reference/copyprivate.md) предложения.  
  
 `shared` применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.4 общих](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Пример  
 В разделе [закрытый](../../../parallel/openmp/reference/private-openmp.md) пример использования `shared`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)