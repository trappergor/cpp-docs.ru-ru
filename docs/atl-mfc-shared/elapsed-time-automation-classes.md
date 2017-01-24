---
title: "Elapsed Time: Automation Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "Automation classes, затраченное время"
  - "calculating dates and times"
  - "вычисления, дата и время"
  - "даты, calculating intervals"
  - "затраченное время, calculating in Automation"
  - "intervals, дата и время"
  - "время, elapsed"
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Elapsed Time: Automation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта процедура показывает, как вычислить разность между объектами `CTime` 2 и получить результат `CTimeSpan`.  
  
#### Вычислить общее затраченное время  
  
1.  Создание объекта `COleDateTime` 2.  
  
2.  Задайте один из объектов `COleDateTime` к текущему времени.  
  
3.  Выполнить некоторую трудоемких задачу.  
  
4.  Установите другой объект `COleDateTime` к текущему времени.  
  
5.  Предположим, что разница между временем 2.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/CPP/elapsed-time-automation-classes_1.cpp)]  
  
## См. также  
 [Date and Time: Automation Support](../Topic/Date%20and%20Time:%20Automation%20Support.md)