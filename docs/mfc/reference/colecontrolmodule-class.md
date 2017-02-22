---
title: "COleControlModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlModule class"
  - "control modules"
  - "MFC ActiveX controls, OLE control modules"
  - "OLE control modules"
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleControlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс, от которого наследуется объект OLE отсека управления.  
  
## Синтаксис  
  
```  
class COleControlModule : public CWinApp  
```  
  
## Заметки  
 Этот класс предоставляет функции\-члены для инициализация отсек управления.  Каждый OLE отсек управления, который использует классы Microsoft foundation может содержать только один объект, производный от `COleControlModule`.  Этот объект создается, когда другие глобальные объекты C\+\+ строятся.  Объявите производный объект `COleControlModule` на глобальном уровне.  
  
 Дополнительные сведения об использовании класса `COleControlModule` см. в описании класса [CWinApp](../../mfc/reference/cwinapp-class.md) и статье [Элементы управления ActiveX](../../mfc/mfc-activex-controls.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [Образец TESTHELP MFC](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)