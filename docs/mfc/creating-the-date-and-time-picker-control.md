---
title: "Создание элемента выбора даты и времени | Microsoft Docs"
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
  - "CDateTimeCtrl - класс, создание"
  - "DateTimePicker - элемент управления [MFC], создание"
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание элемента выбора даты и времени
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Как элемент управления " выбор даты и времени создается зависит от того, используется ли элемент управления в диалоговом окне или создать его в окне nondialog.  
  
### Использовать CDateTimeCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон, добавьте элемент управления " выбор даты и времени в ресурс шаблона диалоговых окон.  Укажите его идентификатор элемента управления.  
  
2.  Определите все требуемые стили, с помощью диалогового окна " Свойства элемента управления " выбор даты и времени.  
  
3.  Используйте [Мастер добавления переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md), чтобы добавить переменную\-член типа [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) со свойством элемента управления.  Можно использовать этот член вызова функции\-члены `CDateTimeCtrl`.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в классе диалогового окна для всех сообщений [уведомление](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) элемента управления " выбор даты времени необходимо обработать \(см. [Сообщения сопоставления в функции](../Topic/Mapping%20Messages%20to%20Functions.md)\).  
  
5.  В окне [OnInitDialog](../Topic/CDialog::OnInitDialog.md) установите все дополнительные стили для объекта `CDateTimeCtrl`.  
  
### Использовать CDateTimeCtrl в окне nondialog  
  
1.  Объявите элемент управления в представлении или класса окна.  
  
2.  Вызовите функцию\-член [Создать](../Topic/CTabCtrl::Create.md) элемента управления, возможно, в [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), возможно начиная с функции обработчика [OnCreate](../Topic/CWnd::OnCreate.md) родительского окна \(если создание подкласса для элемента управления\).  Задайте стили для элемента управления.  
  
## См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)