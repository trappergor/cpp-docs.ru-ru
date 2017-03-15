---
title: "Controls in Dialog Boxes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], dialog boxes"
  - "dialog box controls, about dialog box controls"
  - "dialog box controls"
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Controls in Dialog Boxes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для добавления элементов управления в диалоговое окно можно использовать вкладку [Редактор диалоговых окон](../mfc/dialog-editor-tab-toolbox.md) в [окне панели элементов](../Topic/Toolbox.md), на которой можно выбрать нужный элемент управления, а затем перетащить его в диалоговое окно.  По умолчанию окно панели элементов автоматически скрывается.  Оно отображается в виде вкладки на левом поле решения, когда открыт редактор диалоговых окон.  Однако, можно изменить настройки окна панели элементов таким образом, чтобы оно отображалось постоянно. Для этого необходимо нажать кнопку\-переключатель **Автоматическое скрытие** в правом верхнем углу окна.  Дополнительные сведения об управлении поведением этого окна см. в разделе [Управление окнами](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md).  
  
 Метод перетаскивания позволяет наиболее быстро и эффективно добавить элемент управления в диалоговое окно и переместить элемент управления в рамках одного диалогового окна, а также из одного диалогового окна в другое.  При перетаскивании позиция элемента управления обозначается пунктирной линией, пока пользователь удерживает кнопку мыши нажатой.  Элементу управления, который добавляется в диалоговое окно методом перетаскивания, присваивается стандартная высота для данного типа элементов управления.  
  
 Когда пользователь добавляет в диалоговое окно элемент управления или когда изменяет его положение, окончательная позиция элемента управления может быть обозначена направляющими или полями, или же сеткой макета, если она включена.  
  
 После того, как элемент управления будет добавлен в диалоговое окно, в [окне свойств](../Topic/Properties%20Window.md) можно будет изменить свойства этого элемента управления, например, заголовок.  Можно выбрать несколько элементов управления и изменить определенные свойства для всей группы сразу.  
  
-   [Добавление, изменение и удаление элементов управления](../mfc/adding-editing-or-deleting-controls.md)  
  
-   [Выбор элементов управления](../mfc/selecting-controls.md)  
  
-   [Изменение размера отдельных элементов управления](../mfc/sizing-individual-controls.md)  
  
-   [Выравнивание элементов управления по размеру](../mfc/making-controls-the-same-width-height-or-size.md)  
  
-   [Задание размера для поля со списком и соответствующего раскрывающегося списка](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [Добавление значений в элемент управления поля со списком](../mfc/adding-values-to-a-combo-box-control.md)  
  
-   [Задание ширины горизонтальной полосы прокрутки](../Topic/Setting%20the%20Width%20of%20a%20Horizontal%20Scroll%20Bar.md)  
  
-   [Упорядочение элементов управления в диалоговых окнах](../mfc/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [Пользовательские элементы управления в редакторе диалогов](../mfc/custom-controls-in-the-dialog-editor.md)  
  
-   [Определение клавиш доступа](../mfc/defining-mnemonics-access-keys.md)  
  
-   [Задание местоположения и размера диалогового окна](../mfc/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [Элементы управления "Диалоговые окна" и типы переменных](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)   
 [Dialog Editor](../mfc/dialog-editor.md)