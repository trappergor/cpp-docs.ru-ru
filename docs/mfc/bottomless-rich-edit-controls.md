---
title: "Элементы управления &quot;Rich Edit&quot; &quot;без дна&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления редактированием с форматированием "без дна""
  - "CRichEditCtrl - класс, без дна"
  - "элементы управления Rich Edit, без дна"
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Элементы управления &quot;Rich Edit&quot; &quot;без дна&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложение может изменить элемент управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\), необходимый, чтобы всегда будет одинаковым размером в качестве его содержимое.  Управление расширенного редактирования поддерживает эту, называемую «бездонную» функцию можно отправить его родительское окно сообщения уведомления [EN\_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983), если размер содержимого изменяется.  
  
 При обработке сообщения уведомления **EN\_REQUESTRESIZE**, его необходимо изменить элемент управления в измерения в определенной структуре [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950).  Приложение может также возвращать любые сведения рядом с элементом управления, чтобы облегчить изменение элемента управления в высоту.  Чтобы изменить размер элемента управления, можно использовать функцию [SetWindowPos](../Topic/CWnd::SetWindowPos.md)`CWnd`.  
  
 Можно по бездонное управление расширенного редактирования отправлять сообщение уведомления **EN\_REQUESTRESIZE** с помощью функции\-члена [RequestResize](../Topic/CRichEditCtrl::RequestResize.md).  Это сообщение может быть полезно в обработчике [OnSize](../Topic/CWnd::OnSize.md).  
  
 Чтобы получать сообщения уведомления **EN\_REQUESTRESIZE** необходимо включить уведомления с помощью функции\-члена `SetEventMask`.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)