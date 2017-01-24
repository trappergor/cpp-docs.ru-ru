---
title: "Обработка отраженных сообщений | Microsoft Docs"
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
  - "обработка сообщений, отраженные сообщения"
  - "отраженные сообщения, обработка"
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка отраженных сообщений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отражение сообщений позволяет обрабатывать сообщения для элемента управления, например, `WM_CTLCOLOR`, **WM\_COMMAND** и **WM\_NOTIFY**, в самому элементу управления.  Это делает элемент управления более храниться и портативным.  Механизм работает с общими элементами управления Windows, так и с ранее называвшиеся элементы управления ActiveX \(элементами управления OLE\).  
  
 Отражение сообщений позволяет повторно использовать в `CWnd`\- производные классы более легко.  Отражение сообщений выполняется через [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md), с помощью средства записи сопоставления сообщений **ON\_XXX\_REFLECT** : например, **ON\_CTLCOLOR\_REFLECT** и **ON\_CONTROL\_REFLECT**.  [Техническое примечание 62](../mfc/tn062-message-reflection-for-windows-controls.md) описание отражение сообщения более подробно.  
  
## Выберите действие.  
  
-   [Дополнительные сведения об отражении сообщения](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Реализуйте отражение сообщения для общего элемента управления](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Реализуйте отражение сообщения для элемента управления ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## См. также  
 [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)