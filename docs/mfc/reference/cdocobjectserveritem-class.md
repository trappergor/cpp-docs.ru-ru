---
title: "CDocObjectServerItem Class | Microsoft Docs"
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
  - "CDocObjectServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServerItem class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Команды OLE\-сервер инструментов специально для серверов DocObject.  
  
## Синтаксис  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServerItem::CDocObjectServerItem](../Topic/CDocObjectServerItem::CDocObjectServerItem.md)|Создает объект `CDocObjectServerItem`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServerItem::GetDocument](../Topic/CDocObjectServerItem::GetDocument.md)|Извлекает указатель на документ, содержащий элемент.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocObjectServerItem::OnHide](../Topic/CDocObjectServerItem::OnHide.md)|Вызывает исключение, если границы пытаются скрывать элемент DocObject.|  
|[CDocObjectServerItem::OnShow](../Topic/CDocObjectServerItem::OnShow.md)|Вызываемый платформой, чтобы сделать активным в\- размещения элемента DocObject.  Если элемент не является DocObject, вызывает [COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md).|  
  
## Заметки  
 `CDocObjectServerItem` определяет функции\-члены переопределяемого метода: [OnHide](../Topic/CDocObjectServerItem::OnHide.md), [OnOpen](http://msdn.microsoft.com/ru-ru/7a9b1363-6ad8-4732-9959-4e35c07644fd) и [OnShow](../Topic/CDocObjectServerItem::OnShow.md).  
  
 Для использования `CDocObjectServerItem`, убедите, что переопределение [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) в `COleServerDoc`\- производный класс возвращает новый объект `CDocObjectServerItem`.  Если требуется изменить какие\-либо возможности в элементе, можно создать новый экземпляр собственного `CDocObjectServerItem`\- производный класс.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в справочнике по *MFC*.  См. также [Первые шаги в интернете. активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md) и [активные документы](../Topic/Active%20Documents%20on%20the%20Internet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## Требования  
 **Header:**  afxdocob.h  
  
## См. также  
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer Class](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem Class](../Topic/COleDocObjectItem%20Class.md)