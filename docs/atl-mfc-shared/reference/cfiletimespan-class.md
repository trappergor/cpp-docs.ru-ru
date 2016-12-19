---
title: "CFileTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileTimeSpan"
  - "ATL.CFileTimeSpan"
  - "ATL::CFileTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTimeSpan class"
  - "shared classes, CFileTimeSpan"
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для управления относительная дата и время, связанные с файлом.  
  
## Синтаксис  
  
```  
  
class CFileTimeSpan  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTimeSpan::CFileTimeSpan](../Topic/CFileTimeSpan::CFileTimeSpan.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTimeSpan::GetTimeSpan](../Topic/CFileTimeSpan::GetTimeSpan.md)|Вызывайте этот метод для извлечения промежуток времени из объекта `CFileTimeSpan`.|  
|[CFileTimeSpan::SetTimeSpan](../Topic/CFileTimeSpan::SetTimeSpan.md)|Вызовите этот метод, чтобы задать временной период объекта `CFileTimeSpan`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTimeSpan::operator \-](../Topic/CFileTimeSpan::operator%20-.md)|Выполняет вычитание в объекте `CFileTimeSpan`.|  
|[CFileTimeSpan::operator \!\=](../Topic/CFileTimeSpan::operator%20!=.md)|Проверяет неравенство двух объектов `CFileTimeSpan`.|  
|[CFileTimeSpan::operator \+](../Topic/CFileTimeSpan::operator%20+.md)|Выполняет сложение в объекте `CFileTimeSpan`.|  
|[CFileTimeSpan::operator \+\=](../Topic/CFileTimeSpan::operator%20+=.md)|Выполняет сложение в объекте `CFileTimeSpan` и присвоить его результат текущему объекту.|  
|[CFileTimeSpan::operator \<](../Topic/CFileTimeSpan::operator%20%3C.md)|Сравнивает 2 объекта `CFileTimeSpan`, чтобы определить, меньшие.|  
|[CFileTimeSpan::operator \<\=](../Topic/CFileTimeSpan::operator%20%3C=.md)|Сравнивает 2 объекта `CFileTimeSpan`, чтобы задать равные или меньшие.|  
|[CFileTimeSpan::operator \=](../Topic/CFileTimeSpan::operator%20=.md)|Оператор присваивания.|  
|[CFileTimeSpan::operator \-\=](../Topic/CFileTimeSpan::operator%20-=.md)|Выполняет вычитание в объекте `CFileTimeSpan` и присвоить его результат текущему объекту.|  
|[CFileTimeSpan::operator \=\=](../Topic/CFileTimeSpan::operator%20==.md)|Определяет равенство двух объектов `CFileTimeSpan`.|  
|[CFileTimeSpan::operator \>](../Topic/CFileTimeSpan::operator%20%3E.md)|Сравнивает 2 объекта `CFileTimeSpan` для указания большого размера.|  
|[CFileTimeSpan::operator \>\=](../Topic/CFileTimeSpan::operator%20%3E=.md)|Сравнивает 2 объекта `CFileTimeSpan` для определения равенства или больше.|  
  
## Заметки  
 Этот класс содержит методы для управления относительные часто сталкиваемые промежутков времени при выполнении операций относительно, когда файл был создания последнего доступа или последнего изменения.  Методы этого класса часто используются в сочетании с объектами [класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md).  
  
## Пример  
 См. пример для [CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md).  
  
## Требования  
 **Header:** atltime.h  
  
## См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime Class](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)