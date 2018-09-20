---
title: Использование всплывающих подсказок в объекте CStatusBarCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f17dff6680209664e9d029404e4ef012b9f12046
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392363"
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

