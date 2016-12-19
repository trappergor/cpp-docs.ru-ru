---
title: "COleDataObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObject"
  - "COleDataObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "буфер обмена [C++], поддержка MFC"
  - "буфер обмена [C++], поддержка OLE"
  - "COleDataObject class"
  - "data transfer [C++]"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], поддержка MFC"
  - "IDataObject interface, MFC encapsulation"
  - "OLE [C++], uniform data transfer"
  - "OLE Clipboard [C++], поддержка"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый в передаче данных для получения данных из буфера обмена в различных форматах, через перетаскивание или из внедренного OLE элемента.  
  
## Синтаксис  
  
```  
class COleDataObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDataObject::COleDataObject](../Topic/COleDataObject::COleDataObject.md)|Создает объект `COleDataObject`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDataObject::Attach](../Topic/COleDataObject::Attach.md)|Вложение указанный объект OLE данных в `COleDataObject`.|  
|[COleDataObject::AttachClipboard](../Topic/COleDataObject::AttachClipboard.md)|Вложение объект данных в системном буфере обмена.|  
|[COleDataObject::BeginEnumFormats](../Topic/COleDataObject::BeginEnumFormats.md)|Подготавливает для одного или нескольких последующих вызовов функций `GetNextFormat`.|  
|[COleDataObject::Detach](../Topic/COleDataObject::Detach.md)|Наконец удаляет связанный объект `IDataObject`.|  
|[COleDataObject::GetData](../Topic/COleDataObject::GetData.md)|Копирует данные из вложенного объекта OLE данных в указанном формате.|  
|[COleDataObject::GetFileData](../Topic/COleDataObject::GetFileData.md)|Копирует данные из вложенного объекта OLE данных в указатель `CFile` в указанном формате.|  
|[COleDataObject::GetGlobalData](../Topic/COleDataObject::GetGlobalData.md)|Копирует данные из вложенного объекта OLE данных в `HGLOBAL` в указанном формате.|  
|[COleDataObject::GetNextFormat](../Topic/COleDataObject::GetNextFormat.md)|Возвращает следующий доступный формат данных.|  
|[COleDataObject::IsDataAvailable](../Topic/COleDataObject::IsDataAvailable.md)|Проверяет, доступны ли данные в указанном формате.|  
|[COleDataObject::Release](../Topic/COleDataObject::Release.md)|Наконец, и освобождает `IDataObject` удаляет связанный объект.|  
  
## Заметки  
 `COleDataObject` не имеет базовый класс.  
  
 Эти типы передачи данных входят источник и назначение.  Реализуется источник данных как объект класса [COleDataSource](../../mfc/reference/coledatasource-class.md).  Когда приложение назначения содержит удаленные данные в нем программа спросит для выполнения операции или вставить из буфера обмена, объект класса `COleDataObject` необходимо создать.  
  
 Этот класс позволяет определить, существует ли данные в указанном формате.  Также можно перечислить форматы или проверять доступные данные ли заданный формат доступен, а затем извлечь данные на предпочитаемом формате.  Получение объектов можно выполнить несколькими способами, включая использование [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL` или структуры **STGMEDIUM**.  
  
 Дополнительные сведения см. в разделе макет [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании объектов данных в приложении см. в статье [Объекты данных и источников данных \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## Иерархия наследования  
 `COleDataObject`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDataSource Class](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [CView::OnDrop](../Topic/CView::OnDrop.md)