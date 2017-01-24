---
title: "Current Time: General Purpose Classes | Microsoft Docs"
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
  - "текущее время, CTime object"
  - "инициализация объектов, with the current time"
  - "процедуры, getting current time"
  - "время, getting current"
  - "время, setting current"
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Current Time: General Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей процедуре показано, как создать объект `CTime` и инициализировать ее с текущим временем.  
  
#### Получить текущее время  
  
1.  Выберите объект `CTime` следующим образом:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Не инициализированы неинициализированных объекты `CTime` для допустимого времени.  
  
2.  Вызовите функцию `CTime::GetCurrentTime` чтобы получить текущий момент от операционной системы.  Эта функция возвращает объект `CTime`, который можно использовать для задания значения `CTime` следующим образом:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_2.cpp)]  
  
     Поскольку функция `GetCurrentTime` статического члена от класса `CTime`, необходимо уточнить имя его с именем класса и оператора разрешения области действия \(`::`\), `CTime::GetCurrentTime()`.  
  
 Конечно, 2 конспектированного этапа объединяются в одну предварительно могут быть выписку программы следующим образом:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_3.cpp)]  
  
## См. также  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)