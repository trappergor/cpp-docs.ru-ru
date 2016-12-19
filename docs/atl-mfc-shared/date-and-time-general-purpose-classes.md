---
title: "Date and Time: General-Purpose Classes | Microsoft Docs"
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
  - "date and time classes"
  - "time classes"
ms.assetid: b8115d7f-428a-4c41-9970-18502f2caca2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается, как использовать преимущества служб библиотеки классов, связанных с общецелевых контролю даты и времени.  Процедуры, описанные включают:  
  
-   [Получение текущего времени](../atl-mfc-shared/current-time-general-purpose-classes.md)  
  
-   [Расчетливое затраченное время](../atl-mfc-shared/elapsed-time-general-purpose-classes.md)  
  
-   [Форматирование строковое представление даты и времени](../atl-mfc-shared/formatting-time-values-general-purpose-classes.md)  
  
 Класс `CTime` предоставляет способ представления легко сведения о дате и времени.  Класс `CTimeSpan` представляет общее затраченное время, как разницу между объектами `CTime` 2.  
  
> [!NOTE]
>  Объекты CTime может использоваться для представления даты между 1\-ое января 1970 и 18\-ого января 2038.  Объекты `CTime` имеют разрешение на 1 секунды.  `CTime` основано на типе данных `time_t`, указанном в *ссылке библиотеки времени выполнения*.  
  
## См. также  
 [Date and Time](../atl-mfc-shared/date-and-time.md)