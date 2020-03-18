---
title: Использование всплывающих подсказок в объекте CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: a607a5fb8c9470df42d12c771865b924891b2dac
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442540"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Использование всплывающих подсказок в объекте CStatusBarCtrl

Чтобы включить подсказки для элемента управления "строка состояния", создайте объект `CStatusBarCtrl` с SBT_TOOLTIPSным стилем.

> [!NOTE]
>  Если для реализации строки состояния используется объект `CStatusBar`, используйте функцию `CStatusBar::CreateEx`. Он позволяет указать дополнительные стили для внедренного объекта `CStatusBarCtrl`.

После успешного создания объекта `CStatusBarCtrl` используйте [CStatusBarCtrl:: сеттиптекст](../mfc/reference/cstatusbarctrl-class.md#settiptext) и [CStatusBarCtrl:: жеттиптекст](../mfc/reference/cstatusbarctrl-class.md#gettiptext) , чтобы задать и получить текст подсказки для определенной панели.

Если подсказка задана, она отображается только в том случае, если в части есть значок без текста или если весь текст не может быть отображен внутри части. Всплывающие подсказки не поддерживаются в простом режиме.

## <a name="see-also"></a>См. также раздел

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
