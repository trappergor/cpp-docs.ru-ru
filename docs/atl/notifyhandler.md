---
title: "NotifyHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NotifyHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NotifyHandler function"
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# NotifyHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Имя функции, указанной третьим параметром макроса `NOTIFY_HANDLER` в сопоставлении сообщений.  
  
## Синтаксис  
  
```  
  
      LRESULT   
      NotifyHandler  
      (  
   int idCtrl,  
   LPNMHDR pnmh,  
   BOOL& bHandled   
);  
```  
  
#### Параметры  
 `idCtrl`  
 Идентификатор элемента управления, отправляющий сообщение.  
  
 *pnmh*  
 Адрес структуры [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514), содержащая код и дополнительной информации уведомления.  Для некоторых сообщений уведомлений, точки этого параметра в большей структуре, которая имеет структуру **NMHDR** в качестве первого элемента.  
  
 `bHandled`  
 Сопоставление сообщений устанавливает `bHandled` к **TRUE**, прежде чем *NotifyHandler* вызываются.  Если *NotifyHandler* не полностью обрабатывает сообщение, оно должно установить `bHandled` к **FALSE** для указания необходимостей дальнейшую обработку сообщения.  
  
## Возвращаемое значение  
 Результат обработки сообщения.  0, если успешно.  
  
## Заметки  
 Пример использования этого обработчика сообщений в сопоставлении сообщений см. в разделе [NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md).  
  
## См. также  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)