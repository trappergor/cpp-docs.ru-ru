---
title: Использование всплывающих подсказок в объекте CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 29d326c708743424686d616bbaf172ccd72481ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374693"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Использование всплывающих подсказок в объекте CStatusBarCtrl

Для включения орудия инструментов `CStatusBarCtrl` для управления панелью состояния создайте объект со стилем SBT_TOOLTIPS.

> [!NOTE]
> Если вы используете `CStatusBar` объект для реализации `CStatusBar::CreateEx` панели статуса, используйте эту функцию. Это позволяет указать дополнительные `CStatusBarCtrl` стили для встроенного объекта.

После `CStatusBarCtrl` успешного создания объекта используйте [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) и [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) для установки и извлечения текста наконечника для определенной панели.

После установки наконечника инструмента он отображается только в том случае, если часть имеет значок и текст, или если весь текст не может отображаться внутри детали. Советы по инструменту не поддерживаются в простом режиме.

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
