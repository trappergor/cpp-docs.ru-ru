---
title: "COleDateTime Class | Microsoft Docs"
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
  - "COleDateTime"
  - "ATL.COleDateTime"
  - "ATL::COleDateTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTime class"
  - "Date - тип данных, MFC encapsulation of"
  - "даты, handling in MFC"
  - "shared classes, COleDateTime"
  - "время, handling in MFC"
  - "time-only values"
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует тип данных `DATE`, используемый в ole\-автоматизации.  
  
## Синтаксис  
  
```  
class COleDateTime  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDateTime::COleDateTime](../Topic/COleDateTime::COleDateTime.md)|Создает объект `COleDateTime`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDateTime::Format](../Topic/COleDateTime::Format.md)|Создает форматированное строковое представление объекта `COleDateTime`.|  
|[COleDateTime::GetAsDBTIMESTAMP](../Topic/COleDateTime::GetAsDBTIMESTAMP.md)|Вызовите этот метод, чтобы получить время в объекте `COleDateTime` как структура данных **DBTIMESTAMP**.|  
|[COleDateTime::GetAsSystemTime](../Topic/COleDateTime::GetAsSystemTime.md)|Вызовите этот метод, чтобы получить время в объекте `COleDateTime` как структура данных [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950).|  
|[COleDateTime::GetAsUDATE](../Topic/COleDateTime::GetAsUDATE.md)|Вызовите этот метод, чтобы получить время в `COleDateTime` как структура данных **UDATE**.|  
|[COleDateTime::GetCurrentTime](../Topic/COleDateTime::GetCurrentTime.md)|Создает объект `COleDateTime`, представляющий текущее время \(функция статического элемента\).|  
|[COleDateTime::GetDay](../Topic/COleDateTime::GetDay.md)|Возвращает день этот объект представляет `COleDateTime` \(от 1 до 31\).|  
|[COleDateTime::GetDayOfWeek](../Topic/COleDateTime::GetDayOfWeek.md)|Возвращает день недели этот объект представляет `COleDateTime` \(воскресенье \= 1\).|  
|[COleDateTime::GetDayOfYear](../Topic/COleDateTime::GetDayOfYear.md)|Возвращает день года этот объект представляет `COleDateTime` \(1\-ое января \= 1\).|  
|[COleDateTime::GetHour](../Topic/COleDateTime::GetHour.md)|Возвращает этот объект `COleDateTime` представляет час \(от 0 до 23\).|  
|[COleDateTime::GetMinute](../Topic/COleDateTime::GetMinute.md)|Возвращает минуту этот объект представляет `COleDateTime` \(от 0 до 59\).|  
|[COleDateTime::GetMonth](../Topic/COleDateTime::GetMonth.md)|Возвращает этот объект `COleDateTime` представляет месяц \(от 1 до 12\).|  
|[COleDateTime::GetSecond](../Topic/COleDateTime::GetSecond.md)|Возвращает второй объект `COleDateTime` представляющий \(от 0 до 59\).|  
|[COleDateTime::GetStatus](../Topic/COleDateTime::GetStatus.md)|Получает состояние \(допустимость\) данного объекта `COleDateTime`.|  
|[COleDateTime::GetYear](../Topic/COleDateTime::GetYear.md)|Возвращает год `COleDateTime` представляет данный объект.|  
|[COleDateTime::ParseDateTime](../Topic/COleDateTime::ParseDateTime.md)|Считывает значение даты и времени из строки и задает значение `COleDateTime`.|  
|[COleDateTime::SetDate](../Topic/COleDateTime::SetDate.md)|Устанавливает значение данного объекта `COleDateTime` равным заданному значению даты \- только для чтения.|  
|[COleDateTime::SetDateTime](../Topic/COleDateTime::SetDateTime.md)|Устанавливает значение данного объекта `COleDateTime` равным заданному значению даты и времени.|  
|[COleDateTime::SetStatus](../Topic/COleDateTime::SetStatus.md)|Устанавливает состояние \(допустимость\) данного объекта `COleDateTime`.|  
|[COleDateTime::SetTime](../Topic/COleDateTime::SetTime.md)|Устанавливает значение данного объекта `COleDateTime` равным заданному значению типа Time \- только для чтения.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[\=\= COleDateTime::operator, COleDateTime::operator \< и т д.](../Topic/COleDateTime%20Relational%20Operators.md)|Сравнение значения `COleDateTime` 2.|  
|[COleDateTime::operator \+, \- COleDateTime::operator](../Topic/COleDateTime::operator%20+,%20-.md)|Add и subtract значения `COleDateTime`.|  
|[COleDateTime::operator \+\=, COleDateTime::operator \- \=](../Topic/COleDateTime::operator%20+=,%20-=.md)|Add и subtract значение `COleDateTime` из данного объекта `COleDateTime`.|  
|[COleDateTime::operator \=](../Topic/COleDateTime::operator%20=.md)|Копирует значение `COleDateTime`.|  
|[ДАТА COleDateTime::operator, COleDateTime::operator Date\*](../Topic/COleDateTime::operator%20DATE.md)|Преобразует значение `COleDateTime` в `DATE` или `DATE*`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDateTime::m\_dt](../Topic/COleDateTime::m_dt.md)|Содержит основные **date** для данного объекта `COleDateTime`.|  
|[COleDateTime::m\_status](../Topic/COleDateTime::m_status.md)|Содержит состояние данного объекта `COleDateTime`.|  
  
## Заметки  
 `COleDateTime` не имеет базовый класс.  
  
 Он один из возможных типов для типа данных [ВАРИАНТ](http://msdn.microsoft.com/ru-ru/e305240e-9e11-4006-98cc-26f4932d2118) ole\-автоматизации.  Значение `COleDateTime` представляет собой абсолютные дату и время.  
  
 Тип `DATE` реализуется в виде значения с плавающей запятой.  Дни измеряются в полночь начиная с 30\-ого декабря 1899.  В следующей таблице показаны некоторые даты и связанные с ними значения:  
  
|Дата|Значение|  
|----------|--------------|  
|В полночь 29\-ое декабря 1899.|\-1.0|  
|29\-ое декабря 1899, 6|\-1.25|  
|В полночь 30\-ое декабря 1899.|0.0|  
|В полночь 31\-ое декабря 1899.|1.0|  
|1\-ое января 1900, 6..|2.25|  
  
> [!CAUTION]
>  Заметка в таблице перед тем как значения дня до полночью будут отрицательными значениями времени дня 30\-ого декабря 1899.  Например, 6:00 AM всегда представляется частичным значение 0,25, независимо от того, является целое число, представляющее день положительным \(после 30\-ого декабря 1899\) или недостатки \(до 30\-ого декабря 1899\).  Это означает, что простое сравнение с плавающей запятой ошибочно отсортированные `COleDateTime`, представляющий 6:00 AM на 12\/29\/1899 по мере **later** того, представляющий 7:00 AM в тот же день.  
  
 Класс `COleDateTime` обрабатывает даты за начиная с 1\-ого января 100, до 31\-ого декабря 9999.  Класс `COleDateTime` используется григорианский календарь. он не поддерживает юлианские даты.  `COleDateTime` игнорирует летнее время.  \(См. [Дата и время: поддержка автоматизации](../Topic/Date%20and%20Time:%20Automation%20Support.md)\).  
  
> [!NOTE]
>  Можно использовать формат `%y`, чтобы извлечь год 2 \- числа только даты, начиная с 1900.  Если используется формат `%y` на дату до 1900, то код вызывает сбой УТВЕРЖДЕНИЯ.  
  
 Этот тип используется также для представления значений даты или времени \- только только для чтения.  По соглашению дата 0 \(30\-ое декабря 1899\) используется для значения времени \- только и времени 00:00 \(полуночи\) для значений даты \- только для чтения.  
  
 При создании объекта `COleDateTime` с помощью дат меньше 100, то принятьа дата, но последующие вызовы `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, и происходит сбой `GetSecond` и равен \-1.  Ранее, можно использовать дат 2 \- числа, но даты необходимо 100 или выше в MFC 4,2 и более поздних версий.  
  
 Чтобы избежать проблем, укажите дату 4 \- числа.  Например:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/CPP/coledatetime-class_1.cpp)]  
  
 Основные арифметические операции для значений `COleDateTime` используют класс [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md) сопровождающий.  Значения `COleDateTimeSpan` определяют интервал времени.  Связь между этими классами похоже на связь между [CTime](../Topic/CTime%20Class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о классах `COleDateTime` и `COleDateTimeSpan` см. в статье [Дата и время: поддержка автоматизации](../Topic/Date%20and%20Time:%20Automation%20Support.md).  
  
## Требования  
 **заголовок:** ATLComTime.h  
  
## См. также  
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CTime Class](../Topic/CTime%20Class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)