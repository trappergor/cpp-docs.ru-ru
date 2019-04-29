---
title: Классы окна фрейма, создаваемые с помощью Мастера приложений
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
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
ms.openlocfilehash: 46da8fc0cb98406bdf97285d7c6f824afd61c4bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392821"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Классы окна фрейма, создаваемые с помощью Мастера приложений

При создания нового MFC проекта **новый проект** диалоговое окно, в дополнение к приложений, классы документов и представлений, мастер приложения создает класс производном фреймового окна для окна главного фрейма приложения. Класс называется `CMainFrame` по умолчанию, а также файлы, которые его содержат называются MAINFRM. H и MAINFRM. CPP.

Если приложение является SDI, ваш `CMainFrame` класс является производным от класса [CFrameWnd](../mfc/reference/cframewnd-class.md).

Если приложение MDI, `CMainFrame` является производным от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). В этом случае `CMainFrame` реализует главного фрейма, который содержит панели меню, панели инструментов и состояние. В мастере приложений не является производным новый класс окна фрейма документа для вас. Вместо этого он использует реализацию по умолчанию в [класс CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md). Платформы MFC создает дочернее окно для размещения каждого представления (который может быть типа `CScrollView`, `CEditView`, `CTreeView`, `CListView`, и т. д), необходимого приложению. Если вам нужно настроить в окне фрейма документа, можно создать новый класс окна фрейма документа (см. в разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md)).

Если вы решили поддержки панели инструментов, класс также имеет переменных-членов типа [CToolBar](../mfc/reference/ctoolbar-class.md) и [CStatusBar](../mfc/reference/cstatusbar-class.md) и `OnCreate` функцию обработчика сообщений для инициализации двух [ панелей элементов управления](../mfc/control-bars.md).

Эти классы окна фрейма работать при создании, но расширяющих функциональность, необходимо добавить переменные-члены и функции-члены. Кроме того, может потребоваться обрабатывать другие сообщения Windows окна классов. Дополнительные сведения см. в разделе [изменение стилей окна созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>См. также

[Классы окна фрейма](../mfc/frame-window-classes.md)<br/>
[Программа MFC или управление файлами исходного кода и заголовков](../build/reference/mfc-program-or-control-source-and-header-files.md)

