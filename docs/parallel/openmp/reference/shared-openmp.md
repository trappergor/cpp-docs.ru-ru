---
title: "Общие (OpenMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90491e6e8b415c79e21b4fa518f7e60327ac823e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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