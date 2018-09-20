---
title: Обработка уведомляющих сообщений элемента управления Tab | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 258a3ee579eca0262dace6d1e69a3b5daf9024f6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409042"
---
# <a name="processing-tab-control-notification-messages"></a>Обработка уведомляющих сообщений элемента управления "Вкладка"

При щелчке вкладки или кнопок, вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) отправляет сообщения уведомления своему родительскому окну. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например при щелчке вкладки, может потребоваться предустановку данных элемента управления на странице перед его отображением.

Обработка сообщения WM_NOTIFY из вкладок в классе представления или диалогового окна. Используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch зависимости от того, какие сообщения уведомления обрабатывается. Список уведомлений, набор вкладок можно отправить своему родительскому окну, см. в разделе **уведомления** раздел [ссылки на элемент управления вкладки](https://msdn.microsoft.com/library/windows/desktop/bb760548) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

