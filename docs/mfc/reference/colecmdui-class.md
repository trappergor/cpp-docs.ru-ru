---
title: "COleCmdUI Class | Microsoft Docs"
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
  - "COleCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "COleCmdUI class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует метод для MFC для обновления состояния объектов, связанных с `IOleCommandTarget`\- управляемых функций интерфейса пользователя приложения.  
  
## Синтаксис  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleCmdUI::COleCmdUI](../Topic/COleCmdUI::COleCmdUI.md)|Создает объект `COleCmdUI`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleCmdUI::Enable](../Topic/COleCmdUI::Enable.md)|Задает или снимите клиринги пометить команды разрешения.|  
|[COleCmdUI::SetCheck](../Topic/COleCmdUI::SetCheck.md)|Устанавливает для состояния on или off шарнирнорычажной команды.|  
|[COleCmdUI::SetText](../Topic/COleCmdUI::SetText.md)|Возвращает строку имени или состояния текст команды.|  
  
## Заметки  
 В приложении, которое не включен для DocObjects, когда пользователь просматривает меню в приложении MFC обрабатываются notifcations **UPDATE\_COMMAND\_UI**.  Присваивается каждому уведомления объект [CCmdUI](../Topic/CCmdUI%20Class.md), можно управлять, отражая состояние заданной команды.  Однако при включении приложение для DocObjects уведомления **UPDATE\_OLE\_COMMAND\_UI** процессов MFC и присвоить объекты `COleCmdUI`.  
  
 `COleCmdUI` позволяет DocObject для получения команды, которые возникают в пользовательском интерфейсе \(например FileNew своего контейнера, открытие печать и т д\) и позволяет контейнеру получать команды, которые возникают в пользовательском интерфейсе DocObject.  Хотя `IDispatch` может использоваться для перенаправления те же команды, `IOleCommandTarget` предоставляет более простой способ запроса и выполнения, поскольку оно использует стандартный набор команд, как правило без аргументов, и никакой информации о типе включен.  `COleCmdUI` можно использовать для включения, обновления и задать другие свойства команд пользовательского интерфейса DocObject.  При необходимости вызова команды, вызовите [COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md).  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).  См. также [Первые шаги в интернете. активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md) и [активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md).  
  
## Иерархия наследования  
 [CCmdUI](../Topic/CCmdUI%20Class.md)  
  
 `COleCmdUI`  
  
## Требования  
 **Header:**  afxdocobj.h  
  
## См. также  
 [CCmdUI Class](../Topic/CCmdUI%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)