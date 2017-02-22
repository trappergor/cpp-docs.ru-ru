---
title: "CTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CTimeSpan"
  - "CTimeSpan"
  - "timespan"
  - "ATL::CTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTimeSpan class"
  - "затраченное время, CTimeSpan object"
  - "shared classes, CTimeSpan"
  - "time span"
  - "время, elapsed"
  - "timespan"
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Количество времени, которое внутренне сохраняется как количество секунд, в течение времени.  
  
## Синтаксис  
  
```  
class CTimeSpan  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTimeSpan::CTimeSpan](../Topic/CTimeSpan::CTimeSpan.md)|Создает объекты `CTimeSpan` различными способами.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTimeSpan::Format](../Topic/CTimeSpan::Format.md)|Преобразует `CTimeSpan` в отформатированную строку.|  
|[CTimeSpan::GetDays](../Topic/CTimeSpan::GetDays.md)|Возвращает значение, представляющее число полных дней в этом `CTimeSpan`.|  
|[CTimeSpan::GetHours](../Topic/CTimeSpan::GetHours.md)|Возвращает значение, представляющее количество часов в текущем \(от 23 до 23\).|  
|[CTimeSpan::GetMinutes](../Topic/CTimeSpan::GetMinutes.md)|Возвращает значение, представляющее количество минут в текущем час \(от 59 до 59\).|  
|[CTimeSpan::GetSeconds](../Topic/CTimeSpan::GetSeconds.md)|Возвращает значение, представляющее число секунд в текущую минуту \(от 59 до 59\).|  
|[CTimeSpan::GetTimeSpan](../Topic/CTimeSpan::GetTimeSpan.md)|Возвращает значение объекта `CTimeSpan`.|  
|[CTimeSpan::GetTotalHours](../Topic/CTimeSpan::GetTotalHours.md)|Возвращает значение, представляющее общее число полных часов в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](../Topic/CTimeSpan::GetTotalMinutes.md)|Возвращает значение, представляющее общее число целых минут в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](../Topic/CTimeSpan::GetTotalSeconds.md)|Возвращает значение, представляющее общее число целых секунд в этом `CTimeSpan`.|  
|[CTimeSpan::Serialize64](../Topic/CTimeSpan::Serialize64.md)|Выполняет сериализацию данных или из архива.|  
  
### Операторы  
  
|||  
|-|-|  
|[\+ – оператор](../Topic/CTimeSpan::operator%20+,%20-.md)|Добавляет и subtract объекты `CTimeSpan`.|  
|[оператор \+\= – \=](../Topic/CTimeSpan::operator%20+=,%20-=.md)|Добавляет объект `CTimeSpan` и subtract и от этого `CTimeSpan`.|  
|[\=\= \- оператор \< т д.](../Topic/CTimeSpan%20Comparison%20Operators.md)|Сравнивает 2 относительных значений времени.|  
  
## Заметки  
 `CTimeSpan` не имеет базовый класс.  
  
 Функции преобразования `CTimeSpan` секунд к различным дням, часы, минуты и секунды.  
  
 Объект `CTimeSpan` хранится в структуре **\_\_time64\_t**, равное 8 байт.  
  
 Класс сопровождающий, [CTime](../Topic/CTime%20Class.md), представляющее абсолютное время.  
  
 Классы `CTime` и `CTimeSpan` не предназначены для вывода.  Так как никакие виртуальные функции, размеры обоих объектов `CTime` и `CTimeSpan` ровно 8 байт.  Большинство функции\-члены встроенный.  
  
 Дополнительные сведения об использовании `CTimeSpan` см. в разделе статьи [Дата и время](../../atl-mfc-shared/date-and-time.md) и [управление временем](../../c-runtime-library/time-management.md) в справочнике по *библиотеке времени выполнения*.  
  
## Требования  
 **Header:**  atltime.h  
  
## См. также  
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)