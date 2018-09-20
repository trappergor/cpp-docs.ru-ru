---
title: Классы панели элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13fe4cd9cc483bccde6a342ef224dfbafab36eca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378564"
---
# <a name="control-bar-classes"></a>Классы панели элементов управления

Панели элементов управления, присоединяются к фрейм окна. Они содержат кнопки, панелями состояния или шаблона диалогового окна. Свободные панелей, также называемый палитры инструментов реализуются путем присоединения их [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) объекта.

## <a name="framework-control-bars"></a>Framework панелей элементов управления

Эти панели элементов управления являются неотъемлемой частью платформы MFC. Они проще в использовании и мощнее, чем панелей, элементов управления Windows, так как они интегрированы с помощью платформы. Большинство приложений MFC использовать эти панели элементов управления, а не панелей элементов управления Windows.

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
Базовый класс для панелей элементов управления MFC, перечисленные в этом разделе. На панели элементов управления является окном, выравнивается по краю фрейма окна. На панели управления может содержать `HWND`-дочерние элементы управления или элементы управления, не зависит от `HWND`, такие как кнопки панели инструментов.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Панель элементов управления, основанный на шаблон диалогового окна.

[CReBar](../mfc/reference/crebar-class.md)<br/>
Поддерживает панель инструментов, которая может содержать дополнительные дочерние окна в форме элементов управления.

[Класс CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
На основе инструментов управления windows, которые не содержат команду кнопками с точечными рисунками `HWND`. Большинство приложений MFC использует этот класс вместо `CToolBarCtrl`.

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
Базовый класс для строки состояния элемента управления windows. Большинство приложений MFC использует этот класс вместо `CStatusBarCtrl`.

## <a name="windows-control-bars"></a>Панели элементов управления Windows

Эти панели элементов управления являются тонкими обертками для соответствующих элементов управления Windows. Так как они не интегрированы с помощью платформы, они сложнее в использовании, чем панелей перечисленных выше. Большинство приложений MFC с помощью перечисленных выше панелей управления.

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
Реализует внутренний элемент управления из `CRebar` объекта.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Окна по горизонтали, обычно разделены на области, в которых приложение может выводить сведения о состоянии.

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Предоставляет функциональные возможности стандартного элемента управления "панель инструментов" Windows.

## <a name="related-classes"></a>Связанные классы

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Небольшое всплывающее окно, которое отображается одна строка текста, описывающая назначение инструмента в приложении.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Обрабатывает постоянного хранения закрепление данные о состоянии для панелей элементов управления.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

