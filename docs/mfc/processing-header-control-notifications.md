---
title: "Обработка уведомлений элемента управления &quot;Заголовок&quot; | Microsoft Docs"
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
  - "CHeaderCtrl - класс, обработка уведомлений"
  - "элементы управления [MFC], заголовок"
  - "уведомления элемента управления "заголовок""
  - "элементы управления "заголовок", обработка уведомлений"
  - "уведомления, обработка для CHeaderCtrl"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка уведомлений элемента управления &quot;Заголовок&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс по в представлении или диалогового окна, используется окно свойств для создания функции обработчика [OnChildNotify](../Topic/CWnd::OnChildNotify.md) с оператор switch для всех сообщений уведомлений заголовок\- элемента управления \([CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)\) необходимо обработать \(см. [Сообщения сопоставления в функции](../Topic/Mapping%20Messages%20to%20Functions.md)\).  Уведомления отправляются родительскому окну, когда пользователь щелкает или дважды щелкните элемент заголовка, перетащить разделитель элементов, и т д  
  
 Сообщения уведомления, связанные с элементом управления " Заголовок ", перечислены в разделе [Связь элемента управления " Заголовок "](http://msdn.microsoft.com/library/windows/desktop/bb775239) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)