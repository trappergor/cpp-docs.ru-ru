---
title: "COleTemplateServer Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleTemplateServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation servers [C++], реализация"
  - "COleTemplateServer class"
  - "link containers [C++]"
  - "OLE link containers"
  - "приложения сервера OLE, COleTemplateServer class"
  - "приложения сервера OLE, managing server documents"
  - "серверы, OLE"
  - "visual editing, серверы"
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleTemplateServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый OLE визуального редактирования для элемента серверы, серверы автоматизации и контейнеры связи \(приложения эти указатели поддержки к embeddings\).  
  
## Синтаксис  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleTemplateServer::COleTemplateServer](../Topic/COleTemplateServer::COleTemplateServer.md)|Создает объект `COleTemplateServer`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleTemplateServer::ConnectTemplate](../Topic/COleTemplateServer::ConnectTemplate.md)|Шаблон документа подключении к базовому объекту `COleObjectFactory`.|  
|[COleTemplateServer::Unregister](../Topic/COleTemplateServer::Unregister.md)|Отменяет регистрацию соответствующий шаблон документа.|  
|[COleTemplateServer::UpdateRegistry](../Topic/COleTemplateServer::UpdateRegistry.md)|Регистрирует тип документа с OLE реестре системы.|  
  
## Заметки  
 Этот класс является производным от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); как правило, можно использовать `COleTemplateServer` напрямую, а не выводящ собственный класс.  `COleTemplateServer` использует объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для управления документов сервера.  Используйте `COleTemplateServer`, реализующий полный сервер, то есть сервер, можно выполнить как автономное приложение.  Полные серверы обычно несколько приложений интерфейса MDI, хотя поддерживаются одинарного приложения интерфейса \(SDI\).  Один объект `COleTemplateServer` требуется для каждого типа документа сервера поддержки приложения. то есть, если серверное приложение поддерживает и листов и диаграмм, необходимо иметь 2 объекта `COleTemplateServer`.  
  
 `COleTemplateServer` переопределяет функцию\-член `OnCreateInstance` указанный `COleObjectFactory`.  Это функция\-член вызывается платформой для создания объекта C\+\+ неправильный тип.  
  
 Дополнительные сведения о серверах см. в статье [Серверы. Реализация сервер](../../mfc/servers-implementing-a-server.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [Образец HIERSVR MFC](../../top/visual-cpp-samples.md)   
 [COleObjectFactory Class](../../mfc/reference/coleobjectfactory-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../Topic/COleServerDoc%20Class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)