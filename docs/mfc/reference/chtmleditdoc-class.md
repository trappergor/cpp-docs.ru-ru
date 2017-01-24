---
title: "CHtmlEditDoc Class | Microsoft Docs"
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
  - "CHtmlEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditDoc class"
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) предоставляет функциональные возможности WebBrowser в контексте редактирования платформы документ\- вид архитектуры MFC.  
  
## Синтаксис  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHtmlEditDoc::CHtmlEditDoc](../Topic/CHtmlEditDoc::CHtmlEditDoc.md)|Создает объект `CHtmlEditDoc`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHtmlEditDoc::GetView](../Topic/CHtmlEditDoc::GetView.md)|Получает вложенный объект `CHtmlEditView` к данному документу.|  
|[CHtmlEditDoc::IsModified](../Topic/CHtmlEditDoc::IsModified.md)|Возвращает значение, показывающее, содержит ли элемент управления WebBrowser связанного представления документ, который был изменен пользователем.|  
|[CHtmlEditDoc::OpenURL](../Topic/CHtmlEditDoc::OpenURL.md)|Открывают URL\-адрес.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 `CHtmlEditDoc`  
  
## Требования  
 **Header:** afxhtml.h  
  
## См. также  
 [Образца HTMLEdit](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)