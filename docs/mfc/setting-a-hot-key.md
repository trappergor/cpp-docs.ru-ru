---
title: Задание сочетания клавиш
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a77aad4881acd04c6dabb6dce90acc01be2cfbc8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281282"
---
# <a name="setting-a-hot-key"></a>Задание сочетания клавиш

Приложение может использовать сведения, предоставляемые сочетания клавиш ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) элемента управления в одном из двух способов:

- Настройте глобальные сочетания клавиш для активации окна nonchild, отправляя [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) сообщение в окно активации.

- Настройка сочетания клавиш конкретного потока путем вызова функции Windows [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
