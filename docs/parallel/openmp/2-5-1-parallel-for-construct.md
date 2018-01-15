---
title: "2.5.1 параллельные конструкция for | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7dcd763b68a78e11c3c33bf3d750a26e88ad02ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="251-parallel-for-construct"></a>2.5.1 Конструкция parallel for
**Параллельных для** директива является ярлыком для **параллельных** область, которая содержит только один **для** директивы. Синтаксис **параллельных для** директивы таков:  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 Эта директива позволяет всех предложениях **параллельных** директивы и **для** директив, за исключением `nowait` предложение с идентичными значения и ограничения. Семантика идентична явно указав **параллельных** директива следовали **для** директивы.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **Параллельные** директив, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **для** директив, см. в разделе [раздел 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) на стр.  
  
-   Предложения данных атрибутов, в разделе [2.7.2 предложения атрибутов совместного использования данных](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.