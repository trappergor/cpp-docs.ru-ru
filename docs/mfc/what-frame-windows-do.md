---
title: "Функция окон фрейма | Microsoft Docs"
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
  - "окна фрейма, об окнах фрейма"
  - "окна фрейма, задачи"
  - "MFC - библиотека, окна фрейма"
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция окон фрейма
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помимо просто обрамлять представление, фреймовые окна за многочисленные задачи, относящиеся к фрейм в соответствии с текущим представлением и с приложением.  [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) наследуется от [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md), поэтому они имеют возможности `CFrameWnd`, так и новые возможности, которые они добавляют.  Примеры включают представления дочерние окна, элементы управления, как кнопки и списки и панели элементов управления, в том числе панелей инструментов, строки состояния и диалоговые панели.  
  
 Фреймовое окно отвечает за управление макет дочерних окон.  В платформе MFC, позициях фреймового окна все панели элементов управления, представлениях и других дочерних окнах в клиентской области.  
  
 Фреймовое окно также переадресует команды с соответствующим представлениям и может отвечать на сообщения уведомлений от окна элемента управления.  
  
## Дополнительные сведения  
  
-   [Панели элементов управления \(их поместили в фреймовое окно\)](../Topic/Control%20Bars.md)  
  
-   [Элемент управления меню, панели элементов управления и сочетания клавиш \(их поместили в фреймовое окно\)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Маршрутизация команд \(из фреймового окна к представлению и другим конечным объекты команды\)](../mfc/command-routing.md)  
  
-   [Архитектура \/View документа](../Topic/Document-View%20Architecture.md)  
  
-   [Панели элементов управления](../Topic/Control%20Bars.md)  
  
-   [Элементы управления](../mfc/controls-mfc.md)  
  
## См. также  
 [Окна фрейма](../mfc/frame-windows.md)