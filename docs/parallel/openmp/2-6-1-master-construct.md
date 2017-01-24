---
title: "2.6.1 master Construct | Microsoft Docs"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.1 master Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Образец** директива определяет структуру, определяющую структурированный блок, который выполняется потоком мастерским рабочей группы.  Синтаксис  **Образец** директива выглядит следующим образом:  
  
```  
#pragma omp master new-line  
   structured-block  
```  
  
 Другие потоки в команде не выполняются, состоящего из блока.  Отсутствует неявный барьера или записи или выйти из главной конструирования.