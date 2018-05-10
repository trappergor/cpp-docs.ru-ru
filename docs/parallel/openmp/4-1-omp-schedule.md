---
title: 4.1 OMP_SCHEDULE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e13332077a40e741f56b5602ac5197bbdfef071
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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