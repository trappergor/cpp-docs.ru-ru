---
title: "CMultiDocTemplate Class | Microsoft Docs"
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
  - "CMultiDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiDocTemplate class"
  - "MDI - интерфейс, шаблон"
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет шаблон документа, реализующий множественный интерфейс MDI.  
  
## Синтаксис  
  
```  
  
class CMultiDocTemplate : public CDocTemplate  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMultiDocTemplate::CMultiDocTemplate](../Topic/CMultiDocTemplate::CMultiDocTemplate.md)|Создает объект `CMultiDocTemplate`.|  
  
## Заметки  
 Приложение MDI используется главное фреймовое окно, так как рабочая область, в которой пользователь может открыть ноль или более фреймовые окна документа, каждый из которых указывает документ.  Подробное описание интерфейса MDI см. в разделе guidelines *интерфейса Windows* for software design.  
  
 Шаблон документа определяет связи между 3 типов классов:  
  
-   Класс документа, который наследуется от [CDocument](../Topic/CDocument%20Class.md).  
  
-   Класс представления, отображающий данные из класса документа, перечисленные выше.  Можно наследовать этот класс [CView](../Topic/CView%20Class.md), `CScrollView`, `CFormView` или `CEditView`.  \(Можно также использовать `CEditView` напрямую\).  
  
-   Класс фреймового окна, который содержит представление.  Для шаблонов документов mdi\-приложения можно наследовать этот класс `CMDIChildWnd` или, если не нужно настраивать функциональности фреймовых окна документа, можно использовать напрямую без создания производного [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) собственный класс.  
  
 Приложение MDI может поддерживать несколько типов документа и документы различных типов, могут быть открыты одновременно.  Приложение имеет один шаблон документа для каждого типа документа, он поддерживает.  Например, если приложение MDI поддерживает и электронные таблицы и текстовые документы, приложения имеется 2 объекта `CMultiDocTemplate`.  
  
 Приложение использует шаблон документов, когда пользователь создает новый документ.  Если приложение поддерживает несколько типов документов, то границы получают имена поддерживаемых типов документа из шаблонов документов и отображает их в списке в диалоговом окне нового файла.  Как только пользователь выбрал тип документа, приложение создает объект класса документа, объект фреймового окна и объект представления и вложение их друг к другу.  
  
 Не нужно вызывать `CMultiDocTemplate` за исключением функций\-членов все конструктора.  Границы обрабатывают объекты `CMultiDocTemplate` для внутреннего использования.  
  
 Дополнительные сведения о `CMultiDocTemplate` см. в разделе [Шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)