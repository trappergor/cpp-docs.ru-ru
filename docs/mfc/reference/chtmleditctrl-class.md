---
title: "CHtmlEditCtrl Class | Microsoft Docs"
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
  - "CHtmlEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrl class"
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.  
  
## Синтаксис  
  
```  
class CHtmlEditCtrl: public CWnd,   
   public CHtmlEditCtrlBase< CHtmlEditCtrl >  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](../Topic/CHtmlEditCtrl::CHtmlEditCtrl.md)|Создает объект `CHtmlEditCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHtmlEditCtrl::Create](../Topic/CHtmlEditCtrl::Create.md)|Создает элемент управления ActiveX WebBrowser и вложение его к объекту `CHtmlEditCtrl`.  Эта функция автоматически переводит элемент управления ActiveX WebBrowser в режим правки.|  
|[CHtmlEditCtrl::GetDHtmlDocument](../Topic/CHtmlEditCtrl::GetDHtmlDocument.md)|Извлекает интерфейс [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx) в документе в текущем загруженном, содержащихся в элементе управления WebBrowser.|  
|[CHtmlEditCtrl::GetStartDocument](../Topic/CHtmlEditCtrl::GetStartDocument.md)|Получает URL\-адрес документа по умолчанию для загрузки, содержащихся в элементе управления WebBrowser.|  
  
## Заметки  
 Размещаемый элемент управления WebBrowser автоматически помещаются в режим правки после его создано.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CHtmlEditCtrlBase](../Topic/CHtmlEditCtrlBase%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CHtmlEditCtrl`  
  
## Требования  
 **Header:** afxhtml.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)