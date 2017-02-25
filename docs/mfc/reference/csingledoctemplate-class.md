---
title: "CSingleDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSingleDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleDocTemplate class"
  - "шаблоны документов, single"
  - "однооконный интерфейс (SDI), приложения"
  - "шаблоны, SDI"
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSingleDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет шаблон документа, реализующий интерфейс одинарного \(SDI\).  
  
## Синтаксис  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSingleDocTemplate::CSingleDocTemplate](../Topic/CSingleDocTemplate::CSingleDocTemplate.md)|Создает объект `CSingleDocTemplate`.|  
  
## Заметки  
 Приложение SDI использует главное фреймовое окно для отображения документа; только один документ может быть открыт синхронно.  
  
 Шаблон документа определяет связь между типами классов: 3  
  
-   Класс документа, который наследуется от **CDocument**.  
  
-   Класс представления, отображающий данные из класса документа, перечисленные выше.  Можно наследовать этот класс `CView`, `CScrollView`, `CFormView` или `CEditView`.  \(Можно также использовать `CEditView` напрямую\).  
  
-   Класс фреймового окна, который содержит представление.  Для шаблонов документов SDI можно наследовать этот класс `CFrameWnd`; если не нужно настраивать функциональности главного фреймового окна, можно использовать напрямую без создания производного `CFrameWnd` собственный класс.  
  
 Приложение SDI обычно поддерживает один тип документа, поэтому он содержит только один объект `CSingleDocTemplate`.  Только один документ может быть открыт синхронно.  
  
 Не нужно вызывать `CSingleDocTemplate` за исключением функций\-членов все конструктора.  Границы обрабатывают объекты `CSingleDocTemplate` для внутреннего использования.  
  
 Дополнительные сведения об использовании `CSingleDocTemplate` см. в разделе [Шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Образец DOCKTOOL MFC](../../top/visual-cpp-samples.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../Topic/CDocument%20Class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)