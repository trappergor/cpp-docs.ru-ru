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
ms.openlocfilehash: 00254bdf49015f26ac257789a15afd1e7f5cc31f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621710"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Классы окна фрейма, создаваемые с помощью Мастера приложений

При создании нового проекта MFC из диалогового окна **Новый проект** в дополнение к классам приложения, документа и представления мастер приложений создает производный класс окна фрейма для основного окна фрейма приложения. Класс вызывается `CMainFrame` по умолчанию, а файлы, содержащие его, называются маинфрм. H и МАИНФРМ. CPP.

Если приложение является SDI, `CMainFrame` класс является производным от класса [CFrameWnd](reference/cframewnd-class.md).

Если приложение является MDI, `CMainFrame` оно является производным от класса [CMDIFrameWnd](reference/cmdiframewnd-class.md). В этом случае `CMainFrame` реализуется основной фрейм, который содержит меню, панель инструментов и строки состояния. Мастер приложений не наследует новый класс фрейма окна документа. Вместо этого используется реализация по умолчанию в [классе CMDIChildWnd](reference/cmdichildwnd-class.md). Платформа MFC создает дочернее окно, в котором будут содержаться все представления (которые могут иметь тип,,, `CScrollView` `CEditView` `CTreeView` `CListView` и т. д.), необходимые приложению. Если необходимо настроить окно фрейма документа, можно создать новый класс фрейма документа-Window (см. раздел [Добавление класса](../ide/adding-a-class-visual-cpp.md)).

Если выбрана поддержка панели инструментов, то класс также содержит переменные-члены типов [CToolBar](reference/ctoolbar-class.md) и [CStatusBar](reference/cstatusbar-class.md) и `OnCreate` функцию обработчика сообщений для инициализации двух [панелей элементов управления](control-bars.md).

Эти классы окон фрейма работают как созданные, но для улучшения их функциональности необходимо добавить переменные-члены и функции-члены. Кроме того, может потребоваться, чтобы классы окон обрабатывали другие сообщения Windows. Дополнительные сведения см. [в разделе изменение стилей окна, созданного MFC](changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>См. также раздел

[Классы окон фрейма](frame-window-classes.md)<br/>
[Программа MFC или управление файлами исходного кода и заголовков](../build/reference/mfc-program-or-control-source-and-header-files.md)
