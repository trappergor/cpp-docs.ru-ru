---
title: Глобальные сочетания клавиш
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 5fdcfbef1db0d20126f8eac144f74f8b92410504
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618740"
---
# <a name="global-hot-keys"></a>Глобальные сочетания клавиш

Глобальный горячий ключ связан с конкретным дочерним окном. Он позволяет пользователю активировать окно из любой части системы. Приложение устанавливает глобальный горячий ключ для конкретного окна, отправляя сообщение [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) в это окно. Например, если `m_HotKeyCtrl` является объектом [CHotKeyCtrl](reference/chotkeyctrl-class.md) и `pMainWnd` является указателем на окно, которое должно быть активировано при нажатии клавиши, можно использовать следующий код для связывания горячего ключа, указанного в элементе управления, с окном, на которое указывает `pMainWnd` .

[!code-cpp[NVC_MFCControlLadenDialog#18](codesnippet/cpp/global-hot-keys_1.cpp)]

Когда пользователь нажимает на глобальную горячую клавишу, указанное окно получает [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand) сообщение, которое указывает **SC_HOTKEY** в качестве типа команды. Это сообщение также активирует окно, которое его получает. Поскольку в этом сообщении не содержатся сведения о нажатии точной клавиши, использование этого метода не позволяет отличать разные горячие клавиши, которые могут быть присоединены к одному и тому же окну. Сочетание клавиш остается действительным до тех пор, пока приложение, которое отправило **WM_SETHOTKEY** , не завершит работу.

## <a name="see-also"></a>См. также раздел

[Использование CHotKeyCtrl](using-chotkeyctrl.md)<br/>
[Элементы управления](controls-mfc.md)
