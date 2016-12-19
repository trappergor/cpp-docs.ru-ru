---
title: "Обработка уведомляющих сообщений в элементах управления списками | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl - класс, обработка уведомлений"
  - "обработка уведомлений"
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка уведомляющих сообщений в элементах управления списками
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Так как пользователи щелкают заголовки столбцов, перетащите Значки, метки правки и т д, элемент управления "Список" \([CListCtrl](../Topic/CListCtrl%20Class.md)\) отправляет сообщения уведомления своему родительскому окну.  Обрабатывайте эти сообщения, если требуется сделать что\-нибудь в ответе.  Например, если пользователь щелкает заголовок столбца, может потребоваться сортировка элементов на основе содержимого нажатого столбца, как в Microsoft Outlook.  
  
 Процесс сообщения **WM\_NOTIFY** из элемента управления "Список" по в представлении или класса диалогового окна.  Используйте окно свойств для создания функции обработчика [OnChildNotify](../Topic/CWnd::OnChildNotify.md) с оператор switch на основе, сообщение уведомления обработки.  
  
 Для списка уведомления элемента управления "Список" отправляет своему родительскому окну см. в разделе [Ссылка управления списка](http://msdn.microsoft.com/library/windows/desktop/bb774737) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## См. также  
 [Использование CListCtrl](../Topic/Using%20CListCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)