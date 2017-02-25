---
title: "CClientDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CClientDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CClientDC class"
  - "CDC - класс, device contexts for client areas"
  - "client-area device context"
  - "device contexts, клиентская область"
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CClientDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позаботит о вызове функции Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) во время разработки и во время [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) удаления.  
  
## Синтаксис  
  
```  
  
class CClientDC : public CDC  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CClientDC::CClientDC](../Topic/CClientDC::CClientDC.md)|Создает объект `CClientDC` подключенный к `CWnd`.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CClientDC::m\_hWnd](../Topic/CClientDC::m_hWnd.md)|`HWND` окна, для которого данный `CClientDC` допустимо.|  
  
## Заметки  
 Это означает, что контекст устройства, связанный с объектом `CClientDC` клиентской области окна.  
  
 Дополнительные сведения о `CClientDC` см. в разделе [контексты устройства](../Topic/Device%20Contexts.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CClientDC`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Класс CDC](../Topic/CDC%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../Topic/CDC%20Class.md)