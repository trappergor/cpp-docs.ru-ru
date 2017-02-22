---
title: "CDataPathProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], асинхронный"
  - "asynchronous controls [C++]"
  - "CDataPathProperty class"
  - "элементы управления OLE [C++], асинхронный"
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует OLE свойство элемента управления, который можно загрузить в асинхронном режиме.  
  
## Синтаксис  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDataPathProperty::CDataPathProperty](../Topic/CDataPathProperty::CDataPathProperty.md)|Создает объект `CDataPathProperty`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDataPathProperty::GetControl](../Topic/CDataPathProperty::GetControl.md)|Извлекает элемент управления OLE асинхронной, связанное с объектом `CDataPathProperty`.|  
|[CDataPathProperty::GetPath](../Topic/CDataPathProperty::GetPath.md)|Извлекает имя пути свойств.|  
|[CDataPathProperty::Open](../Topic/CDataPathProperty::Open.md)|Начинает загрузку асинхронного свойства для связанного элемента управления ActiveX \(OLE\).|  
|[CDataPathProperty::ResetData](../Topic/CDataPathProperty::ResetData.md)|Вызывает `CAsyncMonikerFile::OnDataAvailable` для уведомления контейнер, что свойства элемента управления изменилось.|  
|[CDataPathProperty::SetControl](../Topic/CDataPathProperty::SetControl.md)|Помещает асинхронное элемент управления ActiveX \(OLE\), связанного со свойством.|  
|[CDataPathProperty::SetPath](../Topic/CDataPathProperty::SetPath.md)|Задает имя пути свойств.|  
  
## Заметки  
 Асинхронные свойств загружаются после синхронной инициализации.  
  
 Класс `CDataPathProperty` является производным от **CAysncMonikerFile**.  Для реализации асинхронных свойства в элементах управления OLE, создайте класс, наследуемый от `CDataPathProperty`, и переопределите [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md).  
  
 Дополнительные сведения о том, как использовать асинхронные моникеры и управления ActiveX в приложениях веб\-частей см. в следующих статьях:  
  
-   [Первые шаги в интернете. Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Первые шаги в интернете. асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [Пытается образ MFC](../../top/visual-cpp-samples.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)