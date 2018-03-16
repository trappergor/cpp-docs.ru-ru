---
title: "4.1 OMP_SCHEDULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE** применяется только к **для** и **параллельных для** директивы, которые имеют тип расписания **среды выполнения**. Размер типа и блока расписание для такие циклы можно задать во время выполнения, задав переменную среды для любого типа распознанных расписание и необязательный *chunk_size*.  
  
 Для **для** и **параллельных для** директивы, которые имеют тип расписания не **среды выполнения**, **OMP_SCHEDULE** учитывается. Значение по умолчанию для этой переменной среды, определяемого реализацией. Если необязательный *chunk_size* имеет значение, значение должно быть положительным. Если *chunk_size* не задано, предполагается значение 1, в частности, за исключением **статических** расписания. Для **статических** расписание, размер блока по умолчанию задано пространство итерации цикла, деленное на количество потоков, которые применены к циклу.  
  
 Пример  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **для** директив, см. в разделе [раздел 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) на стр.  
  
-   **Параллельные для** директив, см. в разделе [раздел 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) стр.