---
title: "Обработка уведомляющих сообщений в выбора даты и времени элементах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs:
- C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 836714f7a7ca17d759d0d71a7cbb30d63fdfaf95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Обработка уведомляющих сообщений в элементах выбора даты и времени
Как пользователи взаимодействуют с датой и элементе управления, элемент управления (`CDateTimeCtrl`) отправляет сообщения уведомления своему родительскому окну обычно объект представления или диалогового окна. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например, в том случае, когда пользователь открывает элемент выбора даты и времени для отображения элемента управления calendar внедренные месяца, **DTN_DROPDOWN** отправляется уведомление.  
  
 Используйте окно свойств для добавления обработчиков уведомлений в родительский класс сообщений, которые необходимо реализовать.  
  
 В следующем списке описываются различные уведомления, отправляемые элементом управления выбора даты и времени.  
  
-   **DTN_DROPDOWN** сообщает родителю, внедренные управляющий элемент календаря будет отображаться. Это уведомление отправляется только если **DTS_UPDOWN** стиль не задан. Дополнительные сведения о этого уведомления в разделе [внедренные управления Календарь месяца](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN_CLOSEUP** уведомляет родительского объекта, содержащего внедренный управляющий элемент календаря будет закрыта. Это уведомление отправляется только если **DTS_UPDOWN** стиль не задан.  
  
-   **DTN_DATETIMECHANGE** сообщает родителю, что произошло изменение в элементе управления.  
  
-   **DTN_FORMAT** сообщает родителю, что требуется текст для отображения в поле обратного вызова. Дополнительные сведения для этого уведомления и полей обратного вызова см. в разделе [использование полей обратного вызова в дате и элементе управления](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_FORMATQUERY** запрашивает родительским для предоставления максимально допустимый размер строки, которое будет отображаться в поле обратного вызова. Обработка этого уведомления позволяет элементу управления правильно вывода на экран привилегиями постоянно, снижение мерцания в отображение элемента управления. Дополнительные сведения о этого уведомления в разделе [использование полей обратного вызова в дате и элементе управления](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_USERSTRING** сообщает родителю, что пользователь закончил редактирование содержимого элемента управления выбора даты и времени. Это уведомление отправляется только если **DTS_APPCANPARSE** набор стилей.  
  
-   **DTN_WMKEYDOWN** сообщает родителю, когда пользователь вводит в поле обратного вызова. Обрабатывать это уведомление, чтобы эмулировать отклик клавиатуры поддерживается для поля без обратного вызова в элемент выбора даты и времени. Дополнительные сведения о этого уведомления в разделе [поддержки поля обратного вызова в элементе управления DTP](http://msdn.microsoft.com/library/windows/desktop/bb761726) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

