---
title: "COleDropSource Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDropSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropSource class"
  - "перетаскивание, drop source"
  - "операции перетаскивания"
  - "drop target, dragging data to"
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleDropSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает данные для перетаскивания в целевой объект перетаскивания.  
  
## Синтаксис  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDropSource::COleDropSource](../Topic/COleDropSource::COleDropSource.md)|Создает объект `COleDropSource`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDropSource::GiveFeedback](../Topic/COleDropSource::GiveFeedback.md)|Изменяет позицию курсора во время операции перетаскивания.|  
|[COleDropSource::OnBeginDrag](../Topic/COleDropSource::OnBeginDrag.md)|Захват мыши маркеров во время операции перетаскивания.|  
|[COleDropSource::QueryContinueDrag](../Topic/COleDropSource::QueryContinueDrag.md)|Проверяет, должен ли перетаскивать продолжить.|  
  
## Заметки  
 Класс [COleDropTarget](../Topic/COleDropTarget%20Class.md) обрабатывает при получении частью операции перетаскивания.  Объект `COleDropSource` отвечает за определение, когда начинается операция перетаскивания, предоставляя обратную связь во время операции перетаскивания и указать, когда операция перетаскивания.  
  
 Чтобы использовать объект `COleDropSource`, просто вызовите конструктор.  Это упрощает процесс определения, какие события, например щелчок мышью, начинающиеся с помощью функции [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md) операции перетаскивания, [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md) или [COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md).  Эти функции создают объект `COleDropSource`.  Можно изменить поведение по умолчанию функций переопределяемого метода `COleDropSource`.  Такие функции\-члены будут Вызываются в нужное время границами.  
  
 Дополнительные сведения об операциях перетаскивания, использующие OLE см. в статье [Перетаскивание \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
 Дополнительные сведения см. в разделе [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleDropSource`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)