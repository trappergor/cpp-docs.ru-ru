---
title: "2.5.2 конструкция parallel sections | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3a76a950d547effccf0b50fa04799814597bc5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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