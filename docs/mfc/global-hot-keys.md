---
title: Глобальные сочетания клавиш
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 59918648ea24fd1e2a86ca786de3081cd6cca2df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508569"
---
# <a name="global-hot-keys"></a>Глобальные сочетания клавиш

Глобальный горячий ключ связан с конкретным дочерним окном. Он позволяет пользователю активировать окно из любой части системы. Приложение устанавливает глобальную горячую клавишу для конкретного окна, отправляя в это окно сообщение [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) . Например, если `m_HotKeyCtrl` является объектом [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) и `pMainWnd` является указателем на окно, которое должно быть активировано при нажатии клавиши, можно использовать следующий код, чтобы связать горячую клавишу, указанную в элементе управления, с окном, на которое указывает `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Когда пользователь нажимает на глобальную горячую клавишу, указанное окно получает сообщение [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand) , которое указывает **SC_HOTKEY** в качестве типа команды. Это сообщение также активирует окно, которое его получает. Поскольку в этом сообщении не содержатся сведения о нажатии точной клавиши, использование этого метода не позволяет отличать разные горячие клавиши, которые могут быть присоединены к одному и тому же окну. Сочетание клавиш остается действительным до тех пор, пока приложение, отправившего **WM_SETHOTKEY** , не завершит работу.

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
