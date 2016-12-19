---
title: "CFileTime Class | Microsoft Docs"
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
  - "ATL::CFileTime"
  - "CFileTime"
  - "ATL.CFileTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTime class"
  - "shared classes, CFileTime"
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для управления дата и значения времени, связанных с файлом.  
  
## Синтаксис  
  
```  
  
   class CFileTime :   
public FILETIME  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTime::CFileTime](../Topic/CFileTime::CFileTime.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTime::GetCurrentTime](../Topic/CFileTime::GetCurrentTime.md)|Эта статическая функция вызывается для получения объекта `CFileTime`, представляющий текущей системной даты и времени.|  
|[CFileTime::GetTime](../Topic/CFileTime::GetTime.md)|Вызывайте этот метод для извлечения время из объекта `CFileTime`.|  
|[CFileTime::LocalToUTC](../Topic/CFileTime::LocalToUTC.md)|Этот метод вызывается для преобразования локального времени файла на времени файла на основе времени в формате UTC.|  
|[CFileTime::SetTime](../Topic/CFileTime::SetTime.md)|Вызовите этот метод, чтобы задать дату и время, который хранит объект `CFileTime`.|  
|[CFileTime::UTCToLocal](../Topic/CFileTime::UTCToLocal.md)|Вызовите этот метод, чтобы преобразовать время на основе времени в формате UTC в локальном времени файла.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTime::operator \-](../Topic/CFileTime::operator%20-.md)|Этот оператор используется для вычитания на объекте `CFileTime` или `CFileTimeSpan`.|  
|[CFileTime::operator \!\=](../Topic/CFileTime::operator%20!=.md)|Этот оператор сравнивает 2 объекта `CFileTime` на неравенство.|  
|[CFileTime::operator \+](../Topic/CFileTime::operator%20+.md)|Этот оператор используется для сложения на объекте `CFileTimeSpan`.|  
|[CFileTime::operator \+\=](../Topic/CFileTime::operator%20+=.md)|Этот оператор используется для сложения на объекте `CFileTimeSpan` и присвоить его результат текущему объекту.|  
|[CFileTime::operator \<](../Topic/CFileTime::operator%20%3C.md)|Этот оператор сравнивает 2 объекта `CFileTime`, чтобы определить, меньшие.|  
|[CFileTime::operator \<\=](../Topic/CFileTime::operator%20%3C=.md)|Этот оператор сравнивает 2 объекта `CFileTime`, чтобы задать равные или меньшие.|  
|[CFileTime::operator \=](../Topic/CFileTime::operator%20=.md)|Оператор присваивания.|  
|[CFileTime::operator \-\=](../Topic/CFileTime::operator%20-=.md)|Этот оператор используется для вычитания на объекте `CFileTimeSpan` и присвоить его результат текущему объекту.|  
|[CFileTime::operator \=\=](../Topic/CFileTime::operator%20==.md)|Этот оператор сравнивает 2 объекта `CFileTime` на равенство.|  
|[CFileTime::operator \>](../Topic/CFileTime::operator%20%3E.md)|Этот оператор сравнивает 2 объекта `CFileTime` для указания большого размера.|  
|[CFileTime::operator \>\=](../Topic/CFileTime::operator%20%3E=.md)|Этот оператор сравнивает 2 объекта `CFileTime` для определения равенства или больше.|  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileTime::Day](../Topic/CFileTime::Day.md)|Статический элемент данных хранения число интервалов 100 нс, составляющих один день.|  
|[CFileTime::Hour](../Topic/CFileTime::Hour.md)|Статический элемент данных хранения число интервалов 100 нс, составляющих один час.|  
|[CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)|Статический элемент данных хранения 100 нс количество интервалов, которые составляют одну миллисекунду.|  
|[CFileTime::Minute](../Topic/CFileTime::Minute.md)|Статический элемент данных хранения 100 нс количество интервалов, которые составляют одну минуту.|  
|[CFileTime::Second](../Topic/CFileTime::Second.md)|Статический элемент данных хранения 100 нс количество интервалов, которые составляют одну секунду.|  
|[CFileTime::Week](../Topic/CFileTime::Week.md)|Статический элемент данных хранения 100 нс количество интервалов, которые составляют одну неделю.|  
  
## Заметки  
 Этот класс содержит методы для управления дата и значения времени, связанных с созданием, доступом и изменением файлов.  Методы этого класса и данные часто используются в сочетании с объектами, `CFileTimeSpan`, в которых описывается относительными значениями времени.  
  
 Значения даты и времени хранятся как 64 разрядное значение, представляющее число 100 нс интервалов с 1\-ого января 1601.  Это формат времени в формате UTC.  
  
 Указывается, что упрощает следующие статические переменные членов const вычисления:  
  
|Переменная\-член|Количество интервалов 100 наносекунд|  
|----------------------|------------------------------------------|  
|Millisecond|10,000|  
|Второй|Millisecond \* 1.000|  
|Минута|Second \* 60|  
|Час|\* 60 Минута|  
|День|Час \* 24|  
|Неделя|День \* 7|  
  
 **Примечание**  Не все файловые системы может запись создание и время последнего доступа и не все файловые системы записать их тем же способом.  Например, в файловой системе Windows NT ТУЧНОЙ создайте момент имеет разрешения на 10 миллисекунд, время записи обладает разрешением на 2 секунд, а время выборки обладает разрешением 1 дня \(даты доступа\).  В образце имеет разрешения NTFS, время 1 часа.  Кроме того, FAT раз записей на диске на время локального времени, но записей NTFS на диске в формате UTC.  Дополнительные сведения см. в разделе [времена файла](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## Иерархия наследования  
 `FILETIME`  
  
 `CFileTime`  
  
## Требования  
 **Header:** atltime.h  
  
## См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan Class](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)