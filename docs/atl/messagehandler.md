---
title: "MessageHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MessageHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MessageHandler function"
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MessageHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MessageHandler** имя функции, указанной вторым параметром макроса `MESSAGE_HANDLER` в сопоставлении сообщений.  
  
## Синтаксис  
  
```  
  
      LRESULT   
      MessageHandler  
      (  
   UINT uMsg,  
   WPARAM wParam,  
   LPARAM lParam,  
   BOOL& bHandled  
);  
```  
  
#### Параметры  
 `uMsg`  
 Указывает сообщение.  
  
 `wParam`  
 Дополнительные сведения, относящиеся к сообщению.  
  
 `lParam`  
 Дополнительные сведения, относящиеся к сообщению.  
  
 `bHandled`  
 Вызываются наборы `bHandled` сопоставления сообщения с **TRUE** перед `MessageHandler`.  Если `MessageHandler` не полностью обрабатывает сообщение, оно должно установить `bHandled` к **FALSE** для указания необходимостей дальнейшую обработку сообщения.  
  
## Возвращаемое значение  
 Результат обработки сообщения.  0, если успешно.  
  
## Заметки  
 Пример использования этого обработчика сообщений в сопоставлении сообщений см. в разделе [MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md).  
  
## См. также  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)