---
title: Обработка уведомляющих сообщений элемента управления Tab | Документы Microsoft
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
ms.openlocfilehash: 462d9177b1f6300eb356d052cbdfff3b85db86a1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928066"
---
# <a name="processing-tab-control-notification-messages"></a>Обработка уведомляющих сообщений элемента управления "Вкладка"
При щелчке вкладки или кнопок, вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) отправляет сообщения уведомления своему родительскому окну. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например при щелчке вкладки, может потребоваться предустановленный набор данных элемента управления на странице перед его отображением.  
  
 Обработка сообщения WM_NOTIFY из вкладок в классе представления или диалогового окна. Используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) обработчик с инструкцией коммутатора на основе обрабатывается которой сообщения уведомления. Список уведомлений элемента управления tab можно отправить своему родительскому окну, в разделе **уведомления** раздел [управления вкладки](http://msdn.microsoft.com/library/windows/desktop/bb760548) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

