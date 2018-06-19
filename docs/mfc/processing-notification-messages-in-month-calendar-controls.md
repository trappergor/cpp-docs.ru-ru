---
title: Обработка уведомляющих сообщений в месяце календарь элементы управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26b4d73284b0cff362ba16248e0906b76c7f52a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346917"
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

