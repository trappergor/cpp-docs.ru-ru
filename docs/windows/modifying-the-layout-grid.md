---
title: "Modifying the Layout Grid | Microsoft Docs"
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
  - "controls [C++], layout grid"
  - "snap to layout grid"
  - "grids, turning on or off"
  - "layout grid in Dialog Editor"
  - "grids, changing size"
ms.assetid: ec31f595-7542-485b-806f-efbaeccc1b3d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Modifying the Layout Grid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для более точного размещения элементов управления на диалоговом окне можно воспользоваться макетной сеткой.  Когда макетная сетка включена, элемент управления "встает на место", обозначенное пунктирными линиями, как намагниченный.  Функцию "привязки к сетке" можно включить и выключить, а также можно изменять размеры ячеек сетки.  
  
### Включение и выключение сетки макета  
  
1.  В меню **формат** выберите пункт **Параметры направляющих**.  
  
2.  В диалоговом окне [Параметры направляющих](../Topic/Guide%20Settings%20Dialog%20Box.md) нажмите кнопку **Сетка**, чтобы включить или отключить сетку.  
  
     Настройками сетки можно управлять в отдельных окнах редактора диалоговых окон. Для этого можно воспользоваться кнопкой **Сетка** в панели инструментов [редактора диалоговых окон](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
### Изменение сетки макета  
  
1.  В меню **формат** выберите пункт **Параметры направляющих**.  
  
2.  В диалоговом окне [Параметры направляющих](../Topic/Guide%20Settings%20Dialog%20Box.md) введите высоту и ширину ячеек сетки в единицах DLU.  Минимальное значение высоты или ширины — 4 DLU.  Дополнительные сведения о единицах DLU см. в разделе [Размещение элементов управления в диалоговых окнах](../mfc/arrangement-of-controls-on-dialog-boxes.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)