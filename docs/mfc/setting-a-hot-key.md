---
title: Задание сочетания клавиш
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a5dc885767137a4e53d1ea0d066944d5f276c38c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508801"
---
# <a name="setting-a-hot-key"></a>Задание сочетания клавиш

Приложение может использовать сведения, предоставляемые сочетания клавиш ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) элемента управления в одном из двух способов:

- Настройте глобальные сочетания клавиш для активации окна nonchild, отправляя [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) сообщение в окно активации.

- Настройка сочетания клавиш конкретного потока путем вызова функции Windows [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

