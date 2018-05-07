---
title: Классы окна фрейма, созданные с помощью мастера приложений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CMainFrame
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3446de072266fdf7661d2e8d8ca0fc968279646
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Классы окна фрейма, создаваемые с помощью Мастера приложений
При использовании [мастер приложения](../ide/creating-desktop-projects-by-using-application-wizards.md) для создания общая схема приложения, а также приложения, документа и классов представления приложения мастер создает класс производного фреймового окна для окна главного фрейма приложения. Класс называется `CMainFrame` по умолчанию, а также файлы, содержащие его именуются MAINFRM. H и MAINFRM. CPP.  
  
 Если ваше приложение SDI, ваш `CMainFrame` класс, производный от класса [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 Если приложение MDI, `CMainFrame` является производным от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). В этом случае `CMainFrame` реализует главного фрейма, содержащего строки меню, панели инструментов и состояние. Мастер приложений не является производным нового класса окна фрейма документа для вас. Вместо этого он использует реализацию по умолчанию в [CMDIChildWnd-класс](../mfc/reference/cmdichildwnd-class.md). Платформа MFC создает дочернее окно для размещения каждого представления (которого может иметь тип `CScrollView`, `CEditView`, `CTreeView`, `CListView`и так далее), необходимого приложению. Если нужно настроить в окне фрейма документа, можно создать новый класс окна фрейма документа (см. [Добавление класса](../ide/adding-a-class-visual-cpp.md)).  
  
 Если выбран для поддержки панели инструментов, класс также имеет переменных-членов типа [CToolBar](../mfc/reference/ctoolbar-class.md) и [CStatusBar](../mfc/reference/cstatusbar-class.md) и `OnCreate` функцию обработки сообщений для инициализации двух [ панелей элементов управления](../mfc/control-bars.md).  
  
 Эти классы окна фрейма работать, как создать, но расширяющих функциональность, необходимо добавить переменные-члены и функции-члены. Кроме того, может потребоваться окна классов обрабатывать другие сообщения Windows. Дополнительные сведения см. в разделе [изменение стилей окна, созданные с MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Классы окна фрейма](../mfc/frame-window-classes.md)   
 [Программа MFC или управление файлами исходного кода и заголовков](../ide/mfc-program-or-control-source-and-header-files.md)

