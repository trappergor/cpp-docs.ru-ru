---
title: "Обработка уведомляющих сообщений элемента управления &quot;Вкладка&quot; | Microsoft Docs"
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
  - "CTabCtrl - класс, обработка уведомлений"
  - "уведомления, обработка в CTabCtrl"
  - "уведомления, элементы управления вкладка"
  - "обработка уведомлений"
  - "элементы управления вкладка, обработка уведомлений"
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка уведомляющих сообщений элемента управления &quot;Вкладка&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Так как пользователи щелкают вкладки или кнопки, элемент управления TAB \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\) отправляет сообщения уведомления своему родительскому окну.  Обрабатывайте эти сообщения, если требуется сделать что\-нибудь в ответе.  Например, если пользователь щелкает на вкладку, может потребоваться указать заранее контрольные данные на странице перед ее открытия.  
  
 Процесс сообщения **WM\_NOTIFY** из элемента управления TAB по в представлении или класса диалогового окна.  Используйте окно свойств для создания функции обработчика [OnChildNotify](../Topic/CWnd::OnChildNotify.md) с оператор switch на основе, сообщение уведомления обработки.  Для списка уведомления элемент управления TAB отправляет своему родительскому окну **Уведомления** см. в разделе [Связь элемента управления "вкладка"](http://msdn.microsoft.com/library/windows/desktop/bb760548) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)