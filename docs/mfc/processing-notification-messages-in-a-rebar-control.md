---
title: "Обработка уведомляющих сообщений в элементах управления главной панели | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22a8b584c309cd6698ddd73449fcbba866111190
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Обработка уведомляющих сообщений в элементах управления главной панели
В родительском классе элемента управления главной панели, создайте `OnChildNotify` функция обработчика с инструкцию switch для любой управления главной панели (`CReBarCtrl`) для обработки сообщений уведомления. Уведомления отправляются родительского окна при перетаскивании объектов на элемент управления главной панели, изменения макета лентами главной панели, а операции удаления зоны из контейнера элементов управления и т. д.  
  
 Следующие сообщения уведомления могут отправляться объект элемента управления главной панели:  
  
-   **RBN_AUTOSIZE** посылается элементом управления главной панели (создана с **RBS_AUTOSIZE** стиль) при главной панели автоматически изменять свои размеры.  
  
-   **RBN_BEGINDRAG** посылается элементом управления главной панели, когда пользователь начинает перетаскивать полосе.  
  
-   **RBN_CHILDSIZE** посылается элементом управления главной панели, когда дочернее окно полосы изменяется.  
  
-   **RBN_DELETEDBAND** посылается элементом управления главной панели, после удаления полосе.  
  
-   **RBN_DELETINGBAND** посылается элементом управления главной панели, когда полосе которой нужно удалить.  
  
-   **RBN_ENDDRAG** посылается элементом управления главной панели, когда пользователь отпускает полосе.  
  
-   **RBN_GETOBJECT** посылается элементом управления главной панели (создана с **RBS_REGISTERDROP** стиль) когда объект перетаскивается на полосе в элементе управления.  
  
-   **RBN_HEIGHTCHANGE** посылается элементом управления главной панели при изменении его высота.  
  
-   **RBN_LAYOUTCHANGED** посылается элементом управления главной панели, когда пользователь изменяет макет элемента управления зоны.  
  
 Дополнительные сведения об этих уведомлений см. в разделе [ссылки на элемент управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774375) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

