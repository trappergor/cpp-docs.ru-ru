---
title: Глобальные сочетания клавиш
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: eedeb0547320c8b421fa72647f51b02f834af300
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273634"
---
# <a name="global-hot-keys"></a>Глобальные сочетания клавиш

Глобальные сочетания клавиш, связанный с конкретной nonchild окна. Она позволяет пользователям активировать окно из любой части системы. Приложение задает глобальные сочетания клавиш для конкретного окна, отправляя [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) сообщение для этого окна. К примеру Если `m_HotKeyCtrl` — [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) объекта и `pMainWnd` является указатель на окно, чтобы активировать при нажатии клавиш, можно использовать следующий код чтобы связать сочетания клавиш, заданные в элементе управления с помощью окна, на которые указывают `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Каждый раз, когда пользователь нажимает Глобальные сочетания клавиш, окна, указанную получает [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand) сообщение, указывающее **SC_HOTKEY** как тип команды. Это сообщение также активирует окно, которое получает его. Так как это сообщение не содержит все сведения о точный ключ, которая была нажата, с помощью этого метода не может различить разные сочетания клавиш, которые могут присваиваться на том же окне. Сочетания клавиш будет существовать до приложение, отправившее **WM_SETHOTKEY** завершает работу.

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
