---
title: Обработка уведомлений элемента управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 539e7411dcc47be17bb10a5322e30a524679ca8c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194215"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"
В классе представления или диалогового окна, используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch для любого заголовка элемента управления ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) для уведомляющих сообщений обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь нажимает кнопку или дважды щелкает элемент заголовка, перетаскивания a разделитель между элементами и т. д.  
  
 Сообщения уведомлений, связанных с элементом управления заголовка перечислены в [ссылки на элемент управления заголовка](https://msdn.microsoft.com/library/windows/desktop/bb775239) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

