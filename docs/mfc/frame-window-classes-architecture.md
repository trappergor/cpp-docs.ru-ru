---
title: "Классы окна фрейма (архитектура) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы окна фрейма, архитектура "документ-представление""
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы окна фрейма (архитектура)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В документе и архитектуре представления, фреймовые окна, содержащие окно представления.  Они также поддерживают иметь вложенные панели элементов управления на них.  
  
 В приложениях \(MDI\) интерфейс MDI, главное окно является производным от `CMDIFrameWnd`.  Он косвенно содержит кадры документов, объекты `CMDIChildWnd`.  Объекты `CMDIChildWnd`, в свою очередь, содержат представления документов.  
  
 В приложениях \(SDI\) однодокументного интерфейса, главное окно, производное от `CFrameWnd`, содержит представление текущего документа.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Базовый класс для фреймового окна приложения SDI главного.  Также базовый класс для всех других классов фреймового окна.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Базовый класс для фреймового окна приложения MDI главного.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Базовый класс для фреймов окна документов приложения MDI.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет фреймовое окно для представления при документа серверного редактирования на месте.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)