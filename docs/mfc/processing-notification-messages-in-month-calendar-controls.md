---
title: "Обработка уведомляющих сообщений в месяце календарь элементы управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75b07973b1410c7f8bbaa527876efa9b9f1481a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Обработка уведомляющих сообщений в элементах управления "Календарь на месяц"
Как пользователи взаимодействуют с элементом управления Календарь месяца (выбор дат или Просмотр другого месяца), элемент управления (`CMonthCalCtrl`) отправляет сообщения уведомления своему родительскому окну обычно объект представления или диалогового окна. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например когда пользователь выбирает новый месяц для просмотра, может предоставляют набор дат, которые необходимо подчеркнуть.  
  
 Используйте окно свойств для добавления обработчиков уведомлений в родительский класс сообщений, которые необходимо реализовать.  
  
 В следующем списке описываются различные уведомления, отправляемые элементом управления Календарь месяца.  
  
-   **MCN_GETDAYSTATE** запрашивает сведения о том, какие дни должны отображаться полужирным шрифтом. Сведения об обработке этого уведомления в разделе [Установка состояния дня элемента управления Календарь месяца](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN_SELCHANGE** сообщает родителю, измененного выбранной даты или диапазона дат.  
  
-   **MCN_SELECT** сообщает родителю, которые были сделаны явно выбирает дату.  
  
## <a name="see-also"></a>См. также  
 [Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

