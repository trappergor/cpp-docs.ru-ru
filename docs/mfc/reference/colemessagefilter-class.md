---
title: "COleMessageFilter Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleMessageFilter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "приложения [OLE], managing interactions"
  - "COleMessageFilter class"
  - "message filters [C++]"
  - "сообщения [C++], OLE"
  - "OLE [C++], managing concurrency"
  - "приложения OLE [C++], managing interactions"
  - "OLE messages"
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleMessageFilter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет взаимодействием параллелизм, необходимый для приложений OLE.  
  
## Синтаксис  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleMessageFilter::COleMessageFilter](../Topic/COleMessageFilter::COleMessageFilter.md)|Создает объект `COleMessageFilter`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleMessageFilter::BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md)|Помещает приложение в многодельное состояние.|  
|[COleMessageFilter::EnableBusyDialog](../Topic/COleMessageFilter::EnableBusyDialog.md)|Включает и блокирует диалоговое окно, которое отображается, когда в приложении занято.|  
|[COleMessageFilter::EnableNotRespondingDialog](../Topic/COleMessageFilter::EnableNotRespondingDialog.md)|Включает и блокирует диалоговое окно, в котором отображается, если в приложении не отвечает.|  
|[COleMessageFilter::EndBusyState](../Topic/COleMessageFilter::EndBusyState.md)|Завершает состояние приложения многодельное.|  
|[COleMessageFilter::OnMessagePending](../Topic/COleMessageFilter::OnMessagePending.md)|Вызываемый платформой для обработки сообщений, пока выполняется вызов OLE.|  
|[COleMessageFilter::Register](../Topic/COleMessageFilter::Register.md)|Регистрирует фильтр сообщений с OLE системные библиотеки DLL.|  
|[COleMessageFilter::Revoke](../Topic/COleMessageFilter::Revoke.md)|Отменяет регистрацию фильтра сообщений с OLE системные библиотеки DLL.|  
|[COleMessageFilter::SetBusyReply](../Topic/COleMessageFilter::SetBusyReply.md)|Определяет ответ на вызов многодельного приложения OLE.|  
|[COleMessageFilter::SetMessagePendingDelay](../Topic/COleMessageFilter::SetMessagePendingDelay.md)|Задает промежуток времени, в течение которого приложение будет ожидать ответа на вызов OLE.|  
|[COleMessageFilter::SetRetryReply](../Topic/COleMessageFilter::SetRetryReply.md)|Определяет ответ многодельному вызывающего приложения к приложению.|  
  
## Заметки  
 Класс `COleMessageFilter` визуального редактирования сервере и удобен в приложение\-контейнерах, а также в приложениях ole\-автоматизации.  Для серверных приложений, вызвав этот класс может использоваться для следующих приложение "занят", чтобы входящие вызовы от других приложение\-контейнеров или отменены или вновь предпринята позже.  Этот класс также можно использовать для определения действие, выполняемое приложением при вызове с именем приложение занято.  
  
 Общее потребление для вызова серверного приложения [BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md) и [EndBusyState](../Topic/COleMessageFilter::EndBusyState.md), когда было бы unsafe для документа или другого доступного объекта OLE, который необходимо удалить.  Эти позвонены в [CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md) во время обновления интерфейса пользователя.  
  
 По умолчанию объект `COleMessageFilter` выделен, когда приложение инициализируется.  Его можно извлечь с [AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md).  
  
 Это расширенный классом; для работы с ним напрямую редко.  
  
 Дополнительные сведения см. в статье [Серверы. Реализация сервер](../../mfc/servers-implementing-a-server.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleMessageFilter`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)