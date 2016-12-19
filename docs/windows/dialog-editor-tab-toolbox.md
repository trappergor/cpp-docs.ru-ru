---
title: "Панель элементов, вкладка &quot;Редактор диалоговых окон&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "Панель элементов [C++], вкладка "Редактор диалоговых окон""
  - "элементы управления [C++], типы"
  - "элементы управления syslink в диалоговых окнах"
  - "пользовательские элементы управления [Visual Studio], диалоговые окна"
  - "элементы управления [C++], стандартные"
  - "Редактор диалоговых окон, создание элементов управления"
  - "элементы управления [C++], добавление в диалоговые окна"
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Панель элементов, вкладка &quot;Редактор диалоговых окон&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вкладка "Редактор диалоговых окон" появляется в [окне "Панель элементов"](../Topic/Toolbox.md) при работе в редакторе диалоговых окон. Чтобы добавить элементы управления в новое диалоговое окно, перетащите их с панели элементов в создаваемое диалоговое окно \(дополнительные сведения см. в разделе [Добавление элемента управления в диалоговое окно](../mfc/adding-a-control-to-a-dialog-box.md)\). Затем можно изменить местонахождение элементов управления или их размеры и форму.  
  
 На панели элементов доступны следующие стандартные элементы управления:  
  
-   [Button \- элемент управления](../mfc/reference/cbutton-class.md)  
  
-   [Элемент управления "Флажок"](../mfc/reference/button-styles.md)  
  
-   [Элемент управления "Поле со списком"](../mfc/reference/ccombobox-class.md)  
  
-   [Элемент управления "Поле ввода"](../Topic/CEdit%20Class.md)  
  
-   Группа  
  
-   [Элемент управления "Список"](../Topic/CListBox%20Class.md)  
  
-   [Элемент управления "Переключатель"](../mfc/reference/button-styles.md)  
  
-   [Элемент управления "Надпись"](../Topic/CStatic%20Class.md)  
  
-   [Элемент управления "Рисунок"](../mfc/reference/cpictureholder-class.md)  
  
-   [Элемент управления Rich Edit 2.0](../mfc/using-cricheditctrl.md)  
  
-   [Элемент управления "Полоса прокрутки"](../mfc/reference/cscrollbar-class.md)  
  
 [Общие элементы управления Windows](../mfc/controls-mfc.md), доступные на панели элементов, предоставляют приложению расширенные функциональные возможности. В их число входят следующее.  
  
-   [Ползунок \- элемент управления](../Topic/Slider%20Control%20Styles.md)  
  
-   [Spin control](../mfc/using-cspinbuttonctrl.md)  
  
-   [Progress control](../mfc/styles-for-the-progress-control.md)  
  
-   [Элемент управления "Сочетание клавиш"](../Topic/Using%20a%20Hot%20Key%20Control.md)  
  
-   [Элемент управления "Список"](../mfc/list-control-and-list-view.md)  
  
-   [Элемент управления "Дерево"](../Topic/Tree%20Control%20Styles.md)  
  
-   [Элемент управления табуляции](../Topic/Tab%20Controls%20and%20Property%20Sheets.md)  
  
-   [Элемент управления "Анимация"](../mfc/using-an-animation-control.md)  
  
-   [Элемент управления "Выбор даты и времени"](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [Элемент управления "Календарь месяца"](../Topic/Month%20Calendar%20Control%20Examples.md)  
  
-   [Элемент управления "IP\-адрес"](../mfc/reference/cipaddressctrl-class.md)  
  
-   [Элемент управления "Расширенное поле со списком"](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [Пользовательский элемент управления](../mfc/custom-controls-in-the-dialog-editor.md)  
  
 Добавить пользовательские элементы управления в диалоговое окно можно, выбрав значок **Пользовательский элемент управления** на панели элементов и перетащив его в свое диалоговое окно. Чтобы добавить элемент управления Syslink, добавьте пользовательский элемент управления, а затем измените свойство **Class** элемента управления на **Syslink**. Свойства обновятся, и появятся свойства элемента управления Syslink. Сведения о классах\-оболочках MFC см. в разделе [CLinkCtrl](../mfc/reference/clinkctrl-class.md).  
  
 Можно также [добавить в создаваемое диалоговое окно элементы ActiveX](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Кроме того, можно настроить окно "Панель элементов", чтобы упростить работу с ним. Дополнительные сведения см. в разделе [Управление элементами и вкладками на панели элементов](http://msdn.microsoft.com/ru-ru/21285050-cadd-455a-b1f5-a2289a89c4db). Например, для упрощения доступа можно поместить элементы управления в окно "Панель элементов". Дополнительные сведения см. в разделе [Диалоговое окно "Настройка области элементов"](http://msdn.microsoft.com/ru-ru/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Дополнительные сведения об использовании элемента управления RichEdit 1.0 с MFC см. в разделе [Использование элемента управления RichEdit 1.0 с MFC](../Topic/Using%20the%20RichEdit%201.0%20Control%20with%20MFC.md).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Элементы управления](../mfc/controls-mfc.md)   
 [Классы элементов управления](../mfc/control-classes.md)   
 [Классы диалоговых окон](../mfc/dialog-box-classes.md)   
 [Стили полосы прокрутки](../mfc/reference/scroll-bar-styles.md)   
 [Примеры элементов управления "Rich Edit"](../Topic/Rich%20Edit%20Control%20Examples.md)   
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [Элементы управления "Диалоговые окна" и типы переменных](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)