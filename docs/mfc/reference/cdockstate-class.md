---
title: "CDockState Class | Microsoft Docs"
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
  - "CDockState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockState class"
  - "dock state"
  - "docking control bars"
  - "docking tool windows"
  - "положение, control bar"
  - "размер"
  - "размер, control bar"
  - "состояния, dockable control bar"
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сериализуемый класс `CObject`, загрузки, выгрузки или очищает состояние одного или нескольких закрепляющего панелей элементов управления в постоянной памяти \(файл\).  
  
## Синтаксис  
  
```  
class CDockState : public CObject  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDockState::Clear](../Topic/CDockState::Clear.md)|Удаляет сведения о состоянии закрепления.|  
|[CDockState::GetVersion](../Topic/CDockState::GetVersion.md)|Получает номер версии, сохраненного состояния панели.|  
|[CDockState::LoadState](../Topic/CDockState::LoadState.md)|Сведения о состоянии извлечение из реестра или ini\-файла.|  
|[CDockState::SaveState](../Topic/CDockState::SaveState.md)|Сохраняет сведения о состоянии в реестр или файлам INI.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDockState::m\_arrBarInfo](../Topic/CDockState::m_arrBarInfo.md)|Массив указателей на сохраненные сведений о состоянии закрепления с одной записью для каждой области элементов управления.|  
  
## Заметки  
 Состояния закрепления включает размер и положение панели и закреплена ли она.  При восстановлении, сохраненного состояния закрепления, `CDockState` проверяет индекс и, если панель не отображается с текущими параметрами экрана, то положение панели `CDockState` панели масштабирует таким образом, что она будет видна.  Главная цель `CDockState` хранить все состояния несколько панелей элементов управления и разрешить то состояние для сохранения и нагрузила или в реестр ini\-файле приложения или в форме бинарной как часть содержимого объекта `CArchive`.  
  
 Панель может быть любой закрепляемая панель элементов управления, в том числе панель инструментов, строк состояния или диалоговую панель.  Объекты `CDockState` записаны и считывают либо из файла через объект `CArchive`.  
  
 [CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md) извлекает сведения о состоянии `CControlBar` полностью фреймового окна возражает и помещает его в объект `CDockState`.  Затем можно записывать содержимое объекта `CDockState` в хранилище с [Serialize](../Topic/CObject::Serialize.md) или [CDockState::SaveState](../Topic/CDockState::SaveState.md).  Если в дальнейшем потребуется восстановить состояние панелей элементов управления в фреймовом окне, можно загрузить состояние с `Serialize` или [CDockState::LoadState](../Topic/CDockState::LoadState.md), а затем использовать [CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md) для применения сохраненное состояние панели элементов управления фреймового окна.  
  
 Дополнительные сведения о закрепление панели элементов управления см. статьи [Панель элементов управления](../Topic/Control%20Bars.md), [Панели инструментов. Элемент закрепление и перемещаемый](../../mfc/docking-and-floating-toolbars.md) и [фреймовые окна](../../mfc/frame-windows.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDockState`  
  
## Требования  
 **Header:**  afxadv.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)