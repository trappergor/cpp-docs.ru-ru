---
title: Общие (OpenMP) | Документация Майкрософт
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
ms.openlocfilehash: b2bc1a0bbf56623feccd4d3bd96f1e719e192d48
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42544510"
---
# <a name="shared-openmp"></a>shared (OpenMP)
Указывает, что один или несколько переменных следует использовать совместно используются всеми потоками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Одну или несколько переменных для совместного использования. Если указано более одной переменной, разделите имена переменных запятыми.  
  
## <a name="remarks"></a>Примечания  
 Другой способ совместного использования переменных потоков — с помощью [copyprivate](../../../parallel/openmp/reference/copyprivate.md) предложение.  
  
 `shared` область применения следующих директив:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.4 общих](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Пример  
 См. в разделе [частного](../../../parallel/openmp/reference/private-openmp.md) пример использования `shared`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)