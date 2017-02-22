---
title: "Elapsed Time: General-Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "calculating dates and times"
  - "вычисления, дата и время"
  - "даты, calculating intervals"
  - "затраченное время"
  - "затраченное время, вычисление"
  - "intervals, дата и время"
  - "время, elapsed"
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Elapsed Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей процедуре показано, как вычислить разность между объектами `CTime` 2 и получить результат `CTimeSpan`.  
  
#### Вычислить общее затраченное время  
  
1.  Используйте объекты `CTime` и `CTimeSpan` для подсчета затраченного времени, следующим образом:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/CPP/elapsed-time-general-purpose-classes_1.cpp)]  
  
     После высчитывали `elapsedTime` можно использовать функции\-члены `CTimeSpan` для извлечения значения фактической компоненты срабатывания.  
  
## См. также  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)