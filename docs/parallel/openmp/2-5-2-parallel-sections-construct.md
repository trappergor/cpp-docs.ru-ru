---
title: 2.5.2 конструкция parallel sections | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6f7a84e322cb273733c6a724ee2563928df8362
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="252-parallel-sections-construct"></a>2.5.2 Конструкция parallel sections
**Параллельные разделы** директива представляет собой ярлык для указания **параллельных** содержит только один регион **разделы** директивы. Семантика идентична явно указав **параллельных** директива следовали **разделы** директивы. Синтаксис **параллельные разделы** директивы таков:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 *Предложение* может принимать одно из предложений, принимаемое **параллельных** и **разделы** директивы, за исключением **nowait** предложения.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **Параллельные** директив, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **разделы** директив, см. в разделе [раздел 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) на стр.