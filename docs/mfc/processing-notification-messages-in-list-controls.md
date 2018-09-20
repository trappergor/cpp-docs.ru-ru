---
title: Обработка уведомляющих сообщений в элементах управления списками | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab312a1ef64ce64ba39b43df722f9aaafa6dcb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410745"
---
# <a name="processing-notification-messages-in-list-controls"></a>Обработка уведомляющих сообщений в элементах управления списками

Как пользователь щелкает заголовки столбцов, перетащите значки, изменить метки и т. д, элементе управления списком ([CListCtrl](../mfc/reference/clistctrl-class.md)) отправляет сообщения уведомления своему родительскому окну. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например когда пользователь щелкает заголовок столбца, может потребоваться Сортировка элементов на основе содержимого выбранного столбца, как в Microsoft Outlook.

Обработка сообщения WM_NOTIFY в элементе управления списком, в классе представления или диалогового окна. Используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch зависимости от того, какие сообщения уведомления обрабатывается.

Список уведомлений, в элементе управления списком можно отправить своему родительскому окну, см. в разделе [ссылки на элемент управления представления списка](/windows/desktop/Controls/list-view-control-reference) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

