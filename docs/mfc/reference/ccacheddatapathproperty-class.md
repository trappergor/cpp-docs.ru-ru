---
title: "CCachedDataPathProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCachedDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], асинхронный"
  - "asynchronous controls [C++]"
  - "CCachedDataPathProperty class"
  - "memory files [C++]"
  - "элементы управления OLE [C++], асинхронный"
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CCachedDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует OLE свойство элемента управления переключения асинхронно и кэшированный в файле памяти.  
  
## Синтаксис  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](../Topic/CCachedDataPathProperty::CCachedDataPathProperty.md)|Создает объект `CCachedDataPathProperty`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CCachedDataPathProperty::m\_Cache](../Topic/CCachedDataPathProperty::m_Cache.md)|Объект `CMemFile`, в котором следует кэшировать данные.|  
  
## Заметки  
 Файл памяти хранится в оперативной памяти, а не на диске и может использоваться для быстрого временных передачи.  
  
 Вместе с **CAysncMonikerFile** и `CDataPathProperty`, `CCachedDataPathProperty` предоставляет функциональные возможности для использования асинхронных OLE моникеров в элементах управления.  С объектами `CCachedDataPathProperty`, можно передавать данные асинхронно с url\-адреса или сохранить источник и сохранить его в файле памяти через общую переменную `m_Cache`.  Все данные хранятся в файле памяти, и нет необходимости переопределять [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) если не планируется контрольных для уведомлений и отвечать.  Например, если перейти большого файла .GIF, чтобы уведомить элемент управления, что больше данных приезжали и они должны перерисовывать, переопределение `OnDataAvailable` чтобы сделать уведомление.  
  
 Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`.  
  
 Дополнительные сведения о том, как использовать асинхронные моникеры и управления ActiveX в приложениях Интернета см. следующие разделы:  
  
-   [Первые шаги в интернете. Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Первые шаги в интернете. асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)