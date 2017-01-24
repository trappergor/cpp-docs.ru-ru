---
title: "CMonthCalCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonthCalCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl class"
  - "стандартные элементы управления, Internet Explorer 4.0"
  - "Internet Explorer 4.0 common controls"
  - "month calendar controls"
  - "month calendar controls, CMonthCalCtrl class"
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMonthCalCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует функциональные возможности элемента управления "Календарь на месяц".  
  
## Синтаксис  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMonthCalCtrl::CMonthCalCtrl](../Topic/CMonthCalCtrl::CMonthCalCtrl.md)|Создает объект `CMonthCalCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMonthCalCtrl::Create](../Topic/CMonthCalCtrl::Create.md)|Создает элемент управления "Календарь на месяц" и вложение его к объекту `CMonthCalCtrl`.|  
|[CMonthCalCtrl::GetCalendarBorder](../Topic/CMonthCalCtrl::GetCalendarBorder.md)|Получает ширину границы текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetCalendarCount](../Topic/CMonthCalCtrl::GetCalendarCount.md)|Извлекает число календарей, отображаемых в текущем элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetCalendarGridInfo](../Topic/CMonthCalCtrl::GetCalendarGridInfo.md)|Извлекает сведения о текущем элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetCalID](../Topic/CMonthCalCtrl::GetCalID.md)|Извлекает идентификатор календаря для текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetColor](../Topic/CMonthCalCtrl::GetColor.md)|Возвращает цвет заданной области элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetCurrentView](../Topic/CMonthCalCtrl::GetCurrentView.md)|Возвращает представление, которое в данный момент отображается текущим элементом управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetCurSel](../Topic/CMonthCalCtrl::GetCurSel.md)|Возвращает системное время как показано в выбранной даты.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](../Topic/CMonthCalCtrl::GetFirstDayOfWeek.md)|Возвращает первый день недели отображаться в крайнем левом столбце календаря.|  
|[CMonthCalCtrl::GetMaxSelCount](../Topic/CMonthCalCtrl::GetMaxSelCount.md)|Извлекает текущее максимальное число дней, которые могут быть выбраны в элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetMaxTodayWidth](../Topic/CMonthCalCtrl::GetMaxTodayWidth.md)|Извлекает максимальная ширина строки "Сегодня" для текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetMinReqRect](../Topic/CMonthCalCtrl::GetMinReqRect.md)|Получает минимальный размер, необходимый для отображения всего месяца в элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetMonthDelta](../Topic/CMonthCalCtrl::GetMonthDelta.md)|Получает скорость прокрутки элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetMonthRange](../Topic/CMonthCalCtrl::GetMonthRange.md)|Возвращает датируют сведения, представляющее минимальное и максимальное размеры отображения элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetRange](../Topic/CMonthCalCtrl::GetRange.md)|Извлекает текущий минимум и максимум датирует задается в элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::GetSelRange](../Topic/CMonthCalCtrl::GetSelRange.md)|Возвращает датируют сведения, представляющий верхнюю и нижнее ограничение диапазона дат, выбранный пользователем.|  
|[CMonthCalCtrl::GetToday](../Topic/CMonthCalCtrl::GetToday.md)|Извлекает данные о дате на дата, указанная как "сегодня" для управления "Календарь на месяц".|  
|[CMonthCalCtrl::HitTest](../Topic/CMonthCalCtrl::HitTest.md)|Определяет, какой раздел управления "Календарь на месяц" в заданной точке на экране.|  
|[CMonthCalCtrl::IsCenturyView](../Topic/CMonthCalCtrl::IsCenturyView.md)|Указывает, является ли текущее представление текущего элемента управления "Календарь на месяц" представление века.|  
|[CMonthCalCtrl::IsDecadeView](../Topic/CMonthCalCtrl::IsDecadeView.md)|Указывает, является ли текущее представление текущего элемента управления "Календарь на месяц" представление декады.|  
|[CMonthCalCtrl::IsMonthView](../Topic/CMonthCalCtrl::IsMonthView.md)|Указывает, является ли текущее представление элемента управления "Календарь на месяц" представление текущего месяца.|  
|[CMonthCalCtrl::IsYearView](../Topic/CMonthCalCtrl::IsYearView.md)|Указывает, является ли текущее представление элемента управления "Календарь на месяц" представление текущего года.|  
|[CMonthCalCtrl::SetCalendarBorder](../Topic/CMonthCalCtrl::SetCalendarBorder.md)|Задает ширину границы текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetCalendarBorderDefault](../Topic/CMonthCalCtrl::SetCalendarBorderDefault.md)|Задает ширину по умолчанию границы текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetCalID](../Topic/CMonthCalCtrl::SetCalID.md)|Задает идентификатор календаря для текущего элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetCenturyView](../Topic/CMonthCalCtrl::SetCenturyView.md)|Устанавливает текущий элемент управления "Календарь на месяц" для отображения представления века.|  
|[CMonthCalCtrl::SetColor](../Topic/CMonthCalCtrl::SetColor.md)|Устанавливает цвет заданной области элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetCurrentView](../Topic/CMonthCalCtrl::SetCurrentView.md)|Устанавливает текущий элемент управления "Календарь на месяц" для отображения указанного представления.|  
|[CMonthCalCtrl::SetCurSel](../Topic/CMonthCalCtrl::SetCurSel.md)|Устанавливает в данный момент выбранную дату для управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md)|Устанавливает отображения дней в элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetDecadeView](../Topic/CMonthCalCtrl::SetDecadeView.md)|Устанавливает текущий элемент управления "Календарь на месяц" в представление декады.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](../Topic/CMonthCalCtrl::SetFirstDayOfWeek.md)|Задает день недели, отображаемый в крайнем левом столбце календаря.|  
|[CMonthCalCtrl::SetMaxSelCount](../Topic/CMonthCalCtrl::SetMaxSelCount.md)|Устанавливает максимальное число дней, которые могут быть выбраны в элементе управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetMonthDelta](../Topic/CMonthCalCtrl::SetMonthDelta.md)|Задает версию прокрутки элемента управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetMonthView](../Topic/CMonthCalCtrl::SetMonthView.md)|Устанавливает текущий элемент управления "Календарь на месяц" для отображения представления месяца.|  
|[CMonthCalCtrl::SetRange](../Topic/CMonthCalCtrl::SetRange.md)|Установка минимума и допустимый максимум датирует для управления "Календарь на месяц".|  
|[CMonthCalCtrl::SetSelRange](../Topic/CMonthCalCtrl::SetSelRange.md)|Устанавливает выделение для элемента управления "Календарь на месяц" к заданному диапазону дат.|  
|[CMonthCalCtrl::SetToday](../Topic/CMonthCalCtrl::SetToday.md)|Задает элемент управления "Календарь" на текущий день.|  
|[CMonthCalCtrl::SetYearView](../Topic/CMonthCalCtrl::SetYearView.md)|Устанавливает текущий элемент управления "Календарь на месяц" в представление года.|  
|[CMonthCalCtrl::SizeMinReq](../Topic/CMonthCalCtrl::SizeMinReq.md)|Обновляет элемент управления "Календарь на месяц" в его минимума, одномесячный размера.|  
|[CMonthCalCtrl::SizeRectToMin](../Topic/CMonthCalCtrl::SizeRectToMin.md)|Для текущего элемента управления "Календарь на месяц" вычисляет наименьший прямоугольник, который может содержать любые календари то совпадение в заданном прямоугольнике.|  
  
## Заметки  
 Элемент управления "Календарь на месяц" предоставляет пользователю с простым интерфейсом календаря, в котором пользователь может выбрать дату.  Пользователь может изменить отображение следующими способами:  
  
-   Прокрутке назад и переадресуйте из ежемесячно.  
  
-   Нажатие Сегодня отправить СМС для отображения текущего дня \(если не используется стиль **MCS\_NOTODAY** \).  
  
-   Выбрать месяц или год из раскрывающегося меню.  
  
 Можно настраивать элемент управления "Календарь на месяц", применяя различные стили на объект при его создании.  Эти стили, описаны в [Стили элемента управления "Календарь на месяц"](http://msdn.microsoft.com/library/windows/desktop/bb760919) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Элемент управления "Календарь на месяц" может указывать на более чем один месяц, но это может свидетельствовать специальные дни \(например праздники\) bolding дата.  
  
 Дополнительные сведения об использовании элемента управления "Календарь на месяц" см. в разделе [Использование CMonthCalCtrl](../Topic/Using%20CMonthCalCtrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CMonthCalCtrl`  
  
## Требования  
 **Header:**  afxdtctl.h  
  
## См. также  
 [MFC просматривает CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl Class](../../mfc/reference/cdatetimectrl-class.md)