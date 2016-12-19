---
title: "Доступ к встроенному элементу управления &quot;Календарь на месяц&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl - класс, доступ к внедренному элементу управления"
  - "CMonthCalCtrl - класс, изменение шрифта"
  - "DateTimePicker - элемент управления [MFC]"
  - "DateTimePicker - элемент управления [MFC], доступ к календарю месяца"
  - "элементы управления "календарь месяца", изменение шрифта"
  - "элементы управления "календарь месяца", встроено в средство выбора даты и времени"
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Доступ к встроенному элементу управления &quot;Календарь на месяц&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Встроенный объект календаря месяца можно получить из объекта `CDateTimeCtrl` с вызовом функцию\-член [GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md).  
  
> [!NOTE]
>  Вложенный элемент управления календаря месяца используется только в том случае, если элемент управления " выбор даты и времени не имеет стиль, **DTS\_UPDOWN** .  
  
 Это полезно, если требуется изменить некоторые атрибуты, прежде чем встроенный элемент управления.  Для этого обработайте уведомление **DTN\_DROPDOWN**, извлечь элемент управления календаря месяца \(с помощью [CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)\) и внесите необходимые изменения.  К сожалению, элемент управления не упорен календарь месяца.  
  
 Другими словами, при создании пользовательских запросов отображение календаря месяца, новый элемент управления календаря перед уведомлением месяца \( **DTN\_DROPDOWN** \).  Элемент управления уничтожается после уведомления \( **DTN\_CLOSEUP** \) закрытый пользователем.  Это означает, что все атрибуты изменения, прежде чем встроенный элемент управления отображается, теряются при встроенный элемент управления закрыт.  
  
 В следующем примере показано использование этой процедуры, обработчик для уведомления **DTN\_DROPDOWN**.  Код изменяет цвет фона календаря месяца, вызвав метод [SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md), в серому цвет.  Код следующим образом.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 Как уже говорилось ранее, все изменения свойств календаря месяца теряются, с 2 исключения, если встроенный элемент управления закрыт.  Первое исключение, цвета календаря месяца, уже был рассмотрен.  Второе исключение шрифт, используемый элементом управления календаря месяца.  Можно изменить шрифт по умолчанию вызовом [CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md), передав дескриптор существующего шрифта.  В следующем примере \(где `m_dtPicker` объект даты и контроля времени\) показан один из возможных метод:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 Как только сохраняется и используется шрифт был изменен, вызвав метод `CDateTimeCtrl::SetMonthCalFont`, новый шрифт в следующий раз элемент управления календаря месяца для отображения.  
  
## См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)