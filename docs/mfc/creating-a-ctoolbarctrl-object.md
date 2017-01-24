---
title: "создание объекта CToolBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl - класс, создание панелей инструментов"
  - "элементы управления панели инструментов [MFC], создание"
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# создание объекта CToolBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекты содержат несколько внутренних структур данных — список растровых изображений образа кнопки, список строк кнопки, метки и список структур `TBBUTTON` — тех связывают изображение или строка с позицией, стилем, состоянием и идентификатор команды кнопки.  Каждый из элементов этих структур данных сокращенное имя, на которое индекс с отсчетом от нуля.  Перед использованием объекта `CToolBarCtrl` необходимо настроить эти структуры данных.  Для списка структуры данных см. в разделе [Элементы управления панели инструментов](https://msdn.microsoft.com/en-us/library/47xcww9x.aspx) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Список строк можно использовать только для меток кнопки; невозможно получить строки из панели инструментов.  
  
 Для использования объекта `CToolBarCtrl`, как правило, выполните следующие действия.  
  
### Использование объекта CToolBarCtrl  
  
1.  Создайте объект [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
2.  Вызовите метод [Создать](../Topic/CToolBarCtrl::Create.md), чтобы создать общий элемент управления панели инструментов Windows и вложить его в объект `CToolBarCtrl`.  Если требуется образы растрового изображения кнопок, добавьте растровые изображения кнопок на панели инструментов с помощью метода [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md).  Если требуется метки строки для кнопок, добавьте строку на панель инструментов с помощью метода [AddString](../Topic/CToolBarCtrl::AddString.md) или [AddStrings](../Topic/CToolBarCtrl::AddStrings.md).  После вызова `AddString` и\/или `AddStrings`, необходимо вызвать метод [AutoSize](../Topic/CToolBarCtrl::AutoSize.md) для получения, что строку или строки отображались.  
  
3.  Добавьте две кнопки на панели инструментов с помощью метода [AddButtons](../Topic/CToolBarCtrl::AddButtons.md).  
  
4.  Если требуется всплывающие подсказки, обработка сообщений **TTN\_NEEDTEXT** в окне " средства, как описано в разделе [Обрабатывать уведомления всплывающей подсказки](../mfc/handling-tool-tip-notifications.md).  
  
5.  Если требуется, чтобы пользователь мог настраивать панель инструментов, обработка сообщения уведомления настройки в окне ", как описано в разделе [Обрабатывать уведомления настройки](../Topic/Handling%20Customization%20Notifications.md).  
  
## См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)