---
title: "COleDataSource Class | Microsoft Docs"
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
  - "COleDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "буфер обмена [C++], поддержка MFC"
  - "буфер обмена [C++], поддержка OLE"
  - "COleDataSource class"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], поддержка MFC"
  - "IDataObject, MFC encapsulation"
  - "OLE [C++], uniform data transfer"
  - "OLE Clipboard [C++], поддержка"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Действует как кэш, из которого приложение задает данные, которые она предложит во время операций передачи данных в буфер обмена или операции перетаскивания.  
  
## Синтаксис  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDataSource::COleDataSource](../Topic/COleDataSource::COleDataSource.md)|Создает объект `COleDataSource`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDataSource::CacheData](../Topic/COleDataSource::CacheData.md)|Данные предложений в указанном формате, используя структуру **STGMEDIUM**.|  
|[COleDataSource::CacheGlobalData](../Topic/COleDataSource::CacheGlobalData.md)|Предоставляет данные в указанном формате, используя `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)|Предоставляет данные в указанном формате, используя отложенной обработки.|  
|[COleDataSource::DelayRenderFileData](../Topic/COleDataSource::DelayRenderFileData.md)|Предоставляет данные в указанном формате в указателе `CFile`.|  
|[COleDataSource::DelaySetData](../Topic/COleDataSource::DelaySetData.md)|Вызываемый для каждого формата, который поддерживается в `OnSetData`.|  
|[COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)|Выполняет операции перетаскивания с источником данных.|  
|[COleDataSource::Empty](../Topic/COleDataSource::Empty.md)|Очищает объект `COleDataSource` данных.|  
|[COleDataSource::FlushClipboard](../Topic/COleDataSource::FlushClipboard.md)|Отображает все данные в буфер обмена.|  
|[COleDataSource::GetClipboardOwner](../Topic/COleDataSource::GetClipboardOwner.md)|Проверяет, что данные, помещенные в буфер обмена все еще существуют.|  
|[COleDataSource::OnRenderData](../Topic/COleDataSource::OnRenderData.md)|Извлекает данные в ходе отложенной обработки.|  
|[COleDataSource::OnRenderFileData](../Topic/COleDataSource::OnRenderFileData.md)|Извлекает данные в `CFile` как часть отложенной обработки.|  
|[COleDataSource::OnRenderGlobalData](../Topic/COleDataSource::OnRenderGlobalData.md)|Извлекает данные в `HGLOBAL` как часть отложенной обработки.|  
|[COleDataSource::OnSetData](../Topic/COleDataSource::OnSetData.md)|Вызываемый для замены данных в `COleDataSource` объект.|  
|[COleDataSource::SetClipboard](../Topic/COleDataSource::SetClipboard.md)|Задает объект `COleDataSource` в буфере обмена.|  
  
## Заметки  
 Можно создавать источники данных OLE.  Кроме того, классы [COleClientItem](../../mfc/reference/coleclientitem-class.md) и создают источники данных OLE [COleServerItem](../../mfc/reference/coleserveritem-class.md) в ответ на функции\-члены `CopyToClipboard` и `DoDragDrop`.  См. раздел [COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md) для краткое описание.  Переопределить функцию\-член `OnGetClipboardData` класса элемента клиента или сервера для добавления дополнительных форматов буфера обмена к данным в источнике данных OLE, созданном для функции\-члена `CopyToClipboard` или `DoDragDrop`.  
  
 В тех случаях, когда необходимо подготовить данные для передачи необходимо создать объект этого класса и заполнения его с данными с помощью наиболее подходящий для конкретных данных.  Способ он будет вставлен в источник данных напрямую влияют by передаются ли данные немедленно \(быстрая отрисовка\) или по требованию \(отложенной обработки\).  Для каждого формата буфера обмена в котором указывается данные путем передачи формат буфера обмена \(и дополнительную структуру [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) \), вызов [DelayRenderData](../Topic/COleDataSource::DelayRenderData.md).  
  
 Дополнительные сведения об источниках данных и передаче данных см. в статье [Объекты данных и источников данных \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  Кроме того, статьи [Разделы буфера обмена](../../mfc/clipboard.md) описывает механизм OLE буфера обмена.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleDataSource`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [Образец HIERSVR MFC](../../top/visual-cpp-samples.md)   
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDataObject Class](../../mfc/reference/coledataobject-class.md)