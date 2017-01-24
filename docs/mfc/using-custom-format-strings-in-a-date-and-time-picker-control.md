---
title: "Использование строк пользовательского формата в элементе выбора даты и времени | Microsoft Docs"
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
  - "CDateTimeCtrl - класс, стиль отображения"
  - "DateTimePicker - элемент управления [MFC]"
  - "DateTimePicker - элемент управления [MFC], стиль отображения"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование строк пользовательского формата в элементе выбора даты и времени
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

По умолчанию элементы управления " выбор даты и времени предоставляют 3 формата \(каждый формат, соответствующий уникальный стиль\) для отображения текущей даты или времени.  
  
-   **DTS\_LONGDATEFORMAT** указывает дату в длинном формате, создавая вывод, например «четверг 3\-е января 2000».  
  
-   **DTS\_SHORTDATEFORMAT** указывает формат даты вкратце, создавая вывод, например «1\/3\/00 ".  
  
-   **DTS\_TIMEFORMAT** указывает время в длинном формате, создавая вывод, например «5:31: 42 PM».  
  
 Однако можно настраивать внешний вид даты или времени с помощью строк настраиваемого формата.  Эта строка состоит из существующих или символов формата, символов nonformat или сочетания из обоих.  Как только строка строится, вызывать в [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md), передав пользовательскую строку.  Элемент управления " выбор даты и времени затем отображается текущее значение с помощью строки пользовательского формата.  
  
 В следующем примере \(где `m_dtPicker` объект `CDateTimeCtrl` \) демонстрируется возможное решение:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/CPP/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Помимо строк настраиваемого формата, управления " выбор даты и времени, также поддерживают [поля обратного вызова](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)