---
title: Использование всплывающих подсказок в объекте CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: a5ebefe3d5daab9917cdb1db7eface09c78b456a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438796"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Использование всплывающих подсказок в объекте CStatusBarCtrl

Чтобы включить всплывающие подсказки для строки состояния, создайте `CStatusBarCtrl` объекта со стилем SBT_TOOLTIPS.

> [!NOTE]
>  Если вы используете `CStatusBar` объекта, чтобы реализовать строка состояния, используйте `CStatusBar::CreateEx` функции. Он позволяет указать дополнительные стили для встроенного `CStatusBarCtrl` объекта.

Один раз `CStatusBarCtrl` объект был успешно создан, используйте [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) и [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) задание и получение текст подсказки для определенной области.

После задания всплывающая подсказка отображается только в том случае, если часть содержит значок и текст, или в том случае, если невозможно отобразить весь текст в части. Всплывающие подсказки не поддерживаются в простом режиме.

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

