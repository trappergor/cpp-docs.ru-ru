---
title: Обработка уведомляющих сообщений в элементах управления списками | Документы Microsoft
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
ms.openlocfilehash: c5412bbf1fcb7e139394b9563965244080e5c179
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932085"
---
# <a name="processing-notification-messages-in-list-controls"></a>Обработка уведомляющих сообщений в элементах управления списками
При нажатии заголовки столбцов, перетащите значки, изменить метки и т. д управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)) отправляет сообщения уведомления своему родительскому окну. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например при щелчке заголовка столбца, может потребоваться Сортировка элементов на основе содержимого выбранного столбца, как Microsoft Outlook.  
  
 Обработка сообщения WM_NOTIFY из списка элемента управления в классе представления или диалогового окна. Используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) обработчик с инструкцией коммутатора на основе обрабатывается которой сообщения уведомления.  
  
 Список уведомлений, элемент управления списка можно отправить своему родительскому окну, в разделе [ссылки на элемент управления представления списка](http://msdn.microsoft.com/library/windows/desktop/bb774737) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

