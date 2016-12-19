---
title: "Создание элемента управления &quot;Календарь на месяц&quot; | Microsoft Docs"
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
  - "CMonthCalCtrl - класс, создание"
  - "элементы управления "календарь месяца""
  - "элементы управления "календарь месяца", создание"
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание элемента управления &quot;Календарь на месяц&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда элемент управления календаря месяца создается зависит от того, используется ли элемент управления в диалоговом окне или создать его в окне nondialog.  
  
### Использовать CMonthCalCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон, добавьте элемент управления календаря месяца в ресурс шаблона диалоговых окон.  Укажите его идентификатор элемента управления.  
  
2.  Определите все требуемые стили, с помощью диалогового окна " Свойства календаря месяца.  
  
3.  Используйте [Мастер добавления переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md), чтобы добавить переменную\-член типа [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) со свойством элемента управления.  Можно использовать этот член вызова функции\-члены `CMonthCalCtrl`.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в классе диалогового окна для всех сообщений уведомлений календаря месяца необходимо обработать \(см. [Сообщения сопоставления в функции](../Topic/Mapping%20Messages%20to%20Functions.md)\).  
  
5.  В окне [OnInitDialog](../Topic/CDialog::OnInitDialog.md) установите все дополнительные стили для объекта `CMonthCalCtrl`.  
  
### Использовать CMonthCalCtrl в окне nondialog  
  
1.  Указать элемент управления в представлении или класса окна.  
  
2.  Вызовите функцию\-член [Создать](../Topic/CMonthCalCtrl::Create.md) элемента управления, возможно, в [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), возможно начиная с функции обработчика [OnCreate](../Topic/CWnd::OnCreate.md) родительского окна \(если создание подкласса для элемента управления\).  Задайте стили для элемента управления.  
  
## См. также  
 [Использование CMonthCalCtrl](../Topic/Using%20CMonthCalCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)