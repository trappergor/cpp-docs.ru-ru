---
title: "Date and Time | Microsoft Docs"
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
  - "даты, MFC - библиотека"
  - "MFC - библиотека, дата и время"
  - "время"
  - "время, программирование MFC"
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC поддерживает несколько различных способов работы с датами и временем.  К ним относятся:  
  
-   Классы времени общего назначения.  Классы [CTime](../Topic/CTime%20Class.md) и [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) инкапсулируют большая часть функций, связанной с ANSI\- стандартной библиотекой времени, которая объявлена в TIME.H.  
  
-   Поддержка системных часов.  С версией MFC 3,0, поддержка была добавлена к `CTime` для Win32 `SYSTEMTIME` и типов данных `FILETIME`.  
  
-   Поддержка автоматизации [тип данных date](../Topic/DATE%20Type.md).  Обозреватель **DATE** создаст датируют, и значения даты и времени.  Классы [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) и [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md) инкапсулируют эта функциональность.  Они работают с классом [COleVariant](../mfc/reference/colevariant-class.md), используя поддержку автоматизации.  
  
## Дополнительные сведения  
  
-   [Дата и время: Классы общего назначения](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
-   [Дата и время: поддержка SYSTEMTIME](../atl-mfc-shared/date-and-time-systemtime-support.md)  
  
-   [Дата и время: поддержка автоматизации](../Topic/Date%20and%20Time:%20Automation%20Support.md)  
  
-   [Дата и время: Поддержка баз данных](../atl-mfc-shared/date-and-time-database-support.md)  
  
## См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)