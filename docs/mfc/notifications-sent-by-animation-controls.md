---
title: "Уведомления, отправленные элементами управления &quot;Анимация&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "элементы управления анимацией [C++], уведомления"
  - "CAnimateCtrl - класс, уведомления"
  - "элементы управления [MFC], анимация"
  - "уведомления, элементы управления анимацией"
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Уведомления, отправленные элементами управления &quot;Анимация&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элемент управления анимацией \([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)\) отправляет 2 другого типа сообщений уведомления.  Уведомления отправляются в форме сообщений [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591).  
  
 Сообщение отправлено [ACN\_START](http://msdn.microsoft.com/library/windows/desktop/bb761891), когда элемент управления анимацией начато воспроизведения отсечение.  Сообщение отправлено [ACN\_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893), когда элемент управления анимацией закончило обработку или останавливает выполнение воспроизведения отсечение.  
  
## См. также  
 [Использование CAnimateCtrl](../Topic/Using%20CAnimateCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)