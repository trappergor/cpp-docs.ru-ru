---
title: "CDocItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocItem class"
  - "client document items"
  - "container document items"
  - "document items"
  - "items, документ"
  - "OLE documents, items"
  - "server documents"
  - "server documents, document items"
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CDocItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для элементов документа, какие компоненты данных документа.  
  
## Синтаксис  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocItem::GetDocument](../Topic/CDocItem::GetDocument.md)|Возвращает документ, в котором находится элемент.|  
|[CDocItem::IsBlank](../Topic/CDocItem::IsBlank.md)|Определяет, содержит ли элемент любая информация.|  
  
## Заметки  
 Объекты `CDocItem` используются для представления OLE элементов и в документах клиента и сервера.  
  
 Дополнительные сведения см. в статье [контейнеры: Реализация контейнера](../../mfc/containers-implementing-a-container.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocItem`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)