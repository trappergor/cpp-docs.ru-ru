---
title: "2.5.2 parallel sections Construct | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.2 parallel sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**параллельные разделах** директива предоставляет форму ярлыка для указания a  **Параллельно** область, содержащая только одно  **Разделы** директива.  Семантика идентична явно defining a **Параллельно** сразу за а директива  **Разделы** директива.  Синтаксис  **параллельные разделах** директива выглядит следующим образом:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block  ]  
   ...  
}  
```  
  
 Предложение может быть одним из предложений, принимаемых **Параллельно** и  **Разделы** директивы, кроме  **nowait** предложение.  
  
## Перекрестные ссылки:  
  
-   **Параллельно** директива см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **Разделы** директива см. в разделе  [Раздел 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) на странице 14.