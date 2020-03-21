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
ms.openlocfilehash: c17ba2b6dd79e8e62baa29bba403c136d16a0d95
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077538"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Классы окна фрейма, создаваемые с помощью Мастера приложений

При создании нового проекта MFC из диалогового окна **Новый проект** в дополнение к классам приложения, документа и представления мастер приложений создает производный класс окна фрейма для основного окна фрейма приложения. Класс называется `CMainFrame` по умолчанию, а файлы, содержащие его, называются МАИНФРМ. H и МАИНФРМ. CPP.

Если приложение является SDI, класс `CMainFrame` является производным от класса [CFrameWnd](../mfc/reference/cframewnd-class.md).

Если приложение является MDI, `CMainFrame` является производным от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). В этом случае `CMainFrame` реализует основной фрейм, который содержит меню, панель инструментов и строки состояния. Мастер приложений не наследует новый класс фрейма окна документа. Вместо этого используется реализация по умолчанию в [классе CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md). Платформа MFC создает дочернее окно, в котором будут содержаться все представления (которые могут иметь тип `CScrollView`, `CEditView`, `CTreeView`, `CListView`и т. д.), которые требуются приложению. Если необходимо настроить окно фрейма документа, можно создать новый класс фрейма документа-Window (см. раздел [Добавление класса](../ide/adding-a-class-visual-cpp.md)).

Если выбрана поддержка панели инструментов, то класс также содержит переменные-члены типов [CToolBar](../mfc/reference/ctoolbar-class.md) и [CStatusBar](../mfc/reference/cstatusbar-class.md) и функцию обработчика сообщений `OnCreate` для инициализации двух [панелей элементов управления](../mfc/control-bars.md).

Эти классы окон фрейма работают как созданные, но для улучшения их функциональности необходимо добавить переменные-члены и функции-члены. Кроме того, может потребоваться, чтобы классы окон обрабатывали другие сообщения Windows. Дополнительные сведения см. [в разделе изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>См. также:

[Классы окна фрейма](../mfc/frame-window-classes.md)<br/>
[Программа MFC или управление файлами исходного кода и заголовков](../build/reference/mfc-program-or-control-source-and-header-files.md)
