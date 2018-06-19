---
title: Обработка уведомлений элемента управления заголовок | Документы Microsoft
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
ms.openlocfilehash: 1a0fe657089c33679cf8d18f95268a70335804c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348895"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"
В классе представления или диалогового окна, используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функция обработчика с инструкцию switch для любого заголовка элемента управления ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) для уведомляющих сообщений обрабатывать (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь нажимает кнопку или дважды щелкает элемент заголовка перетаскивания a разделитель между элементами и т. д.  
  
 Сообщения уведомлений, связанный с элементом управления заголовка перечислены в [ссылки на элемент управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775239) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

