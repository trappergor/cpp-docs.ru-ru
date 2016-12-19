---
title: "CDocObjectServer Class | Microsoft Docs"
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
  - "CDocObjectServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServer class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует дополнительные интерфейсы OLE, необходимые, чтобы сделать сервер `COleDocument` в обычный полный сервер DocObject: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` и `IPrint`.  
  
## Синтаксис  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServer::CDocObjectServer](../Topic/CDocObjectServer::CDocObjectServer.md)|Создает объект `CDocObjectServer`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServer::ActivateDocObject](../Topic/CDocObjectServer::ActivateDocObject.md)|Активировать сервер объекта документа, но не отображает его.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServer::OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)|Отображает представление DocObject.|  
|[CDocObjectServer::OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)|Извлекает состояние представления DocObject.|  
|[CDocObjectServer::OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)|Сохраняет состояние представления DocObject.|  
  
## Заметки  
 `CDocObjectServer` является производным от `CCmdTarget` и рабочих сотрудничестве с `COleServerDoc` чтобы предоставить интерфейсы.  
  
 Документ сервера DocObject может содержать объекты [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md), которые представляют интерфейс сервера к элементам DocObject.  
  
 Настраивать сервер DocObject, создайте собственный класс, производный от `CDocObjectServer` и переопределить его представление настройте функции [OnActivateView](../Topic/CDocObjectServer::OnActivateView.md), [OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md) и [OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md).  Необходимо предоставить новый экземпляр класса в ответ на вызов платформы.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в справочнике по *MFC*.  См. также [Первые шаги в интернете. активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md) и [активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md).  
  
 Также см. в следующей статье базы знаний Майкрософт:  
  
-   Q247382: PRB. Подсказки для элементов управления ActiveX на сервере документа скрыты контейнером документа ActiveX  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocObjectServer`  
  
## Требования  
 **Header:**  afxdocob.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)