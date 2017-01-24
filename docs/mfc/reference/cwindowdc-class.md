---
title: "CWindowDC Class | Microsoft Docs"
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
  - "CWindowDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowDC class"
  - "device contexts, окно"
  - "screen output classes"
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindowDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Производное от `CDC`.  
  
## Синтаксис  
  
```  
class CWindowDC : public CDC  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindowDC::CWindowDC](../Topic/CWindowDC::CWindowDC.md)|Создает объект `CWindowDC`.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindowDC::m\_hWnd](../Topic/CWindowDC::m_hWnd.md)|Объект `HWND`, к которому присоединен этот элемент `CWindowDC`.|  
  
## Заметки  
 Вызывает функцию Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)во время создания [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) во время уничтожения.  Это означает, что объект `CWindowDC` осуществляет доступ к целой области экрана [CWnd](../Topic/CWnd%20Class.md) \(клиентские и неклиентские области\).  
  
 Дополнительные сведения об использовании `CWindowDC` см. в разделе [Контексты устройств](../Topic/Device%20Contexts.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CWindowDC`  
  
## Требования  
 Заголовок: afxwin.h  
  
## См. также  
 [Класс CDC](../Topic/CDC%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../Topic/CDC%20Class.md)