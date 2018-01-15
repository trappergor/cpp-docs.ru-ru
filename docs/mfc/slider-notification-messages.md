---
title: "Уведомляющие сообщения ползунка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a4fc9e9065017e04b6375d1e5a8e336d4366755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="slider-notification-messages"></a>Уведомляющие сообщения ползунка
Элемент управления "ползунок" уведомляет родительского окна действий пользователя, отправляя родительского `WM_HSCROLL` или `WM_VSCROLL` сообщений, в зависимости от ориентации элемента управления "ползунок". Чтобы обработать эти сообщения, добавьте обработчики для `WM_HSCROLL` и `WM_VSCROLL` сообщений родительского окна. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) функции-члены будут передаваться код уведомления, положение ползунка и указатель на [CSliderCtrl](../mfc/reference/csliderctrl-class.md) объекта. Обратите внимание, что указатель имеет тип **CScrollBar \***  несмотря на то, что он указывает `CSliderCtrl` объекта. Может потребоваться выполнить приведение этого указателя, если необходимо работать с элементом управления "ползунок".  
  
 Вместо использования прокрутки штрих-кодов уведомления, элементы управления "ползунок" Отправить другой набор кодов уведомления. Отправляет элемент управления "ползунок" **TB_BOTTOM**, **TB_LINEDOWN**, **TB_LINEUP**, и **TB_TOP** уведомления коды только в том случае, когда пользователь взаимодействует с элементом управления "ползунок" с помощью клавиатуры. **TB_THUMBPOSITION** и **TB_THUMBTRACK** сообщения уведомления отправляются только в том случае, когда пользователь использует мышь. **TB_ENDTRACK**, **TB_PAGEDOWN**, и **TB_PAGEUP** коды уведомления отправляются в обоих случаях.  
  
 В следующей таблице перечислены уведомляющих сообщений элемента управления "ползунок" и события (коды виртуальных клавиш или события мыши), которые вызывают отправку уведомлений. (Список стандартных кодов виртуального ключа, см. в Winuser.h.)  
  
|Сообщение уведомления|События, что приводит к отправке уведомления|  
|--------------------------|-------------------------------------------|  
|**TB_BOTTOM**|**VK_END**|  
|**TB_ENDTRACK**|`WM_KEYUP`(пользователь выпущена ключ, который отправлен соответствующий виртуальному коду клавиши.)|  
|**TB_LINEDOWN**|**VK_RIGHT** или **VK_DOWN**|  
|**TB_LINEUP**|**VK_LEFT** или **VK_UP**|  
|**TB_PAGEDOWN**|**VK_NEXT** (пользователь щелкнул ниже или правее ползунка канала)|  
|**TB_PAGEUP**|**VK_PRIOR** (пользователь щелкнул канал выше или слева от ползунка)|  
|**TB_THUMBPOSITION**|`WM_LBUTTONUP`После **TB_THUMBTRACK** сообщение уведомления|  
|**TB_THUMBTRACK**|Перемещение ползунка (пользователь перетащить ползунок)|  
|**TB_TOP**|**VK_HOME**|  
  
## <a name="see-also"></a>См. также  
 [Использование CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

