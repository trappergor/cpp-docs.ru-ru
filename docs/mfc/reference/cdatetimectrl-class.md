---
title: "CDateTimeCtrl Class | Microsoft Docs"
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
  - "CDateTimeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl class"
  - "date-picking functionality"
  - "DateTimePicker control [MFC]"
  - "DateTimePicker control [MFC], CDateTimeCtrl class"
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует функциональные возможности управления " выбор даты и времени.  
  
## Синтаксис  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDateTimeCtrl::CDateTimeCtrl](../Topic/CDateTimeCtrl::CDateTimeCtrl.md)|Создает объект `CDateTimeCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDateTimeCtrl::CloseMonthCal](../Topic/CDateTimeCtrl::CloseMonthCal.md)|Закрывает элемент управления " выбор текущей даты и времени.|  
|[CDateTimeCtrl::Create](../Topic/CDateTimeCtrl::Create.md)|Создается элемент управления " выбор даты и времени и вложение его к объекту `CDateTimeCtrl`.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](../Topic/CDateTimeCtrl::GetDateTimePickerInfo.md)|Извлекает сведения о текущем элементе управления " выбор даты и времени.|  
|[CDateTimeCtrl::GetIdealSize](../Topic/CDateTimeCtrl::GetIdealSize.md)|Возвращает оптимальный размер элемента управления " выбор даты и времени, необходимого для показывает текущую дату или время.|  
|[CDateTimeCtrl::GetMonthCalColor](../Topic/CDateTimeCtrl::GetMonthCalColor.md)|Возвращает цвет для данной части календарного месяца в элементе управления " выбор даты и времени.|  
|[CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)|Извлекает объект `CMonthCalCtrl`, связанный с элементом управления выбора даты и времени.|  
|[CDateTimeCtrl::GetMonthCalFont](../Topic/CDateTimeCtrl::GetMonthCalFont.md)|Получает шрифт в настоящий момент, используемый элементом управления "Календарь на месяц" дочернего элемента управления " выбор даты и времени.|  
|[CDateTimeCtrl::GetMonthCalStyle](../Topic/CDateTimeCtrl::GetMonthCalStyle.md)|Возвращает стиль текущей управления " выбор даты и времени.|  
|[CDateTimeCtrl::GetRange](../Topic/CDateTimeCtrl::GetRange.md)|Извлекает текущий минимально и максимально допустимые раз системы для управления " выбор даты и времени.|  
|[CDateTimeCtrl::GetTime](../Topic/CDateTimeCtrl::GetTime.md)|Извлекает выбранный в данный момент времени из элемента управления " выбор даты и времени и помещает его в указанную структуру `SYSTEMTIME`.|  
|[CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md)|Задает отображение управления выбора даты и времени, в соответствии с заданной строкой форматирования.|  
|[CDateTimeCtrl::SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)|Задает ключ цвета для данной части календарного месяца в элементе управления " выбор даты и времени.|  
|[CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)|Задает шрифт, элемент управления "Календарь на месяц" дочернего элемента управления " выбор даты и времени будет использоваться.|  
|[CDateTimeCtrl::SetMonthCalStyle](../Topic/CDateTimeCtrl::SetMonthCalStyle.md)|Задает стиль текущей управления " выбор даты и времени.|  
|[CDateTimeCtrl::SetRange](../Topic/CDateTimeCtrl::SetRange.md)|Задает минимально и максимально допустимые раз системы для управления " выбор даты и времени.|  
|[CDateTimeCtrl::SetTime](../Topic/CDateTimeCtrl::SetTime.md)|Задает время в элементе управления " выбор даты и времени.|  
  
## Заметки  
 Элемент управления " выбор даты и времени \(DTP\) элемент управления предоставляет простой интерфейс для обмена сведения о дате и времени с пользователем.  Этот интерфейс содержит поля, каждый из которых указывает часть сведения о дате и времени, хранящиеся в элементе управления.  Пользователь может изменить данные, которые хранятся в элементе управления, изменяя содержимое строки в данном поле.  Пользователь может перемещать из поля с полем с помощью мыши или клавиатуры.  
  
 Можно настраивать элемент управления " выбор даты и времени, применяя различные стили на объект при его создании.  См. раздел [Средство выбора даты и времени контролируют стили](http://msdn.microsoft.com/library/windows/desktop/bb761728) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] дополнительные сведения о стилях, относящихся к элементу управления " выбор даты и времени.  Можно установить формат отображения управления DTP с помощью стилей формата.  Эти стили форматирования, описаны в разделе "форматом вставки стилей" в разделе [Средство выбора даты и времени контролируют стили](http://msdn.microsoft.com/library/windows/desktop/bb761728)[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 Элемент управления " выбор даты и времени также использует уведомления и обратных вызовов, которые описаны в [Использование CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CDateTimeCtrl`  
  
## Требования  
 **Header:**  afxdtctl.h  
  
## См. также  
 [Образца CMNCTRL1 MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl Class](../../mfc/reference/cmonthcalctrl-class.md)