---
title: "Классы окна фрейма, создаваемые с помощью Мастера приложений | Microsoft Docs"
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
  - "CMainFrame"
  - "CMainFrame::PreCreateWindow"
  - "CMainFrame.PreCreateWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастера приложений [C++], классы окна фрейма, созданные"
  - "CFrameWnd - класс, окна фрейма"
  - "классы [C++], окно фрейма"
  - "CMainFrame - класс"
  - "CMDIChildWnd - класс, окна фрейма"
  - "CMDIFrameWnd - класс, окна фрейма"
  - "классы окна фрейма, создано мастерами приложений"
  - "классы окон"
  - "классы окон, фрейм"
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы окна фрейма, создаваемые с помощью Мастера приложений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании [Мастер приложений](../ide/creating-desktop-projects-by-using-application-wizards.md), чтобы создать общую схему приложения, в дополнение к применению, документ и классы представления, мастер приложений создает производный класс фреймового окна фрейма окна для основного приложения.  Класс называется `CMainFrame` по умолчанию и файлы, содержащие его называют MAINFRM.H и MAINFRM.CPP.  
  
 Если приложение SDI, класс `CMainFrame` является производным от класса [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 Если приложение MDI, `CMainFrame` наследуется от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md).  В этом случае `CMainFrame` реализует большую ЭВМ, которая хранит меню, панели инструментов и строки состояния.  Мастер приложений не является новый класс фреймового окна документа автоматически.  Вместо этого он использует реализацию по умолчанию в [Класс CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  Платформы MFC создает дочернее окно, чтобы содержать все представления \(это может быть типа `CScrollView`, `CEditView`, `CTreeView`, `CListView` и т д\), требует приложение.  Если необходимо настраивать в фрейме окна документа, можно создать новый класс фреймового окна документа \(см. [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)\).  
  
 При выборе поддержки панель инструментов, класс также содержит переменные\-члены типа [CToolBar](../mfc/reference/ctoolbar-class.md) и [CStatusBar](../mfc/reference/cstatusbar-class.md) и функции обработчика сообщений `OnCreate` для инициализации 2 [панели элементов управления](../Topic/Control%20Bars.md).  
  
 Эти классы фреймового окна работают так создается, но увеличить их функциональные возможности, необходимо добавить переменные\-члены и функции\-члены.  Кроме того, можно иметь классов окна обрабатывать другие сообщения Windows.  Дополнительные сведения см. в разделе [Изменение стилей окна с MFC](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md).  
  
## См. также  
 [Классы окна фрейма](../mfc/frame-window-classes.md)   
 [Программа MFC или управление файлами исходного кода и заголовков](../ide/mfc-program-or-control-source-and-header-files.md)