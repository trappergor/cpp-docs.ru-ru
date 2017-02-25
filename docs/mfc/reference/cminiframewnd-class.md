---
title: "CMiniFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMiniFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMiniFrameWnd class"
  - "mini-frame windows"
  - "панели инструментов [C++]"
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMiniFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет фреймовое окно половин\- высоты обычно увиденное вокруг перемещаемых панелей инструментов.  
  
## Синтаксис  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMiniFrameWnd::CMiniFrameWnd](../Topic/CMiniFrameWnd::CMiniFrameWnd.md)|Создает объект `CMiniFrameWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMiniFrameWnd::Create](../Topic/CMiniFrameWnd::Create.md)|Создает объект `CMiniFrameWnd` после создания.|  
|[CMiniFrameWnd::CreateEx](../Topic/CMiniFrameWnd::CreateEx.md)|Создает объект `CMiniFrameWnd` \(с дополнительными параметрами\) после конструирования.|  
  
## Заметки  
 Эти окна области ведут себя как обычные фреймовые окна, за исключением того, что они не имеют кнопки свернуть и развернуть или меню и должны только один нажмите кнопку закрыть в меню система.  
  
 Чтобы использовать объект `CMiniFrameWnd`, сначала укажите объект.  Затем вызовите функцию\-член [Создание](../Topic/CMiniFrameWnd::Create.md) для отображения окна области.  
  
 Дополнительные сведения о том, как использовать объекты `CMiniFrameWnd` см. в статье [Элемент закрепление панели инструментов и перемещаемые](../../mfc/docking-and-floating-toolbars.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)