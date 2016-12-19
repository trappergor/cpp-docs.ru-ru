---
title: "CRichEditDoc Class | Microsoft Docs"
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
  - "CRichEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditDoc class"
  - "document/view architecture, элементы управления Rich Edit"
  - "документы, rich edit"
  - "OLE containers, rich edit"
  - "элементы управления Rich Edit, OLE container"
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) предоставляет функциональные возможности управления расширенного редактирования в контексте архитектуры представления документов MFC.  
  
## Синтаксис  
  
```  
  
class CRichEditDoc : public COleServerDoc  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditDoc::CreateClientItem](../Topic/CRichEditDoc::CreateClientItem.md)|Вызываемый для выполнения очистки документа.|  
|[CRichEditDoc::GetStreamFormat](../Topic/CRichEditDoc::GetStreamFormat.md)|Указывает, должны ли вход и выход потока включать сведения о форматировании.|  
|[CRichEditDoc::GetView](../Topic/CRichEditDoc::GetView.md)|Извлекает asssociated объект [CRichEditView](../../mfc/reference/cricheditview-class.md).|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditDoc::m\_bRTF](../Topic/CRichEditDoc::m_bRTF.md)|Указывает, должен ли поток ВВОДА\-ВЫВОДА включить форматирование.|  
  
## Заметки  
 Элемент управления" окно "расширенного редактирования, в котором пользователь может вводить и редактирования текста.  Текст можно присвоить символ и форматирование абзаца, и может включать внедренные объект OLE.  Управления расширенного редактирования предоставляют программный интерфейс для форматирования текста.  Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для операций форматирования, доступным для пользователя.  
  
 `CRichEditView` поддерживает характерные текст и форматирование текста.  `CRichEditDoc` ведет список элементов клиента, в представлении.  `CRichEditCntrItem` предоставляет доступ к элементам OLE контейнер\- на стороне клиента.  
  
 Это общее \(элемент управления Windows и, следовательно, [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) и связанные классы\) доступны только для программ, выполняемых в рамках версии 3.51 в Windows 95 и Windows NT \/98 и более поздних версий.  
  
 Пример использования расширенного редактирования документа в приложении MFC см. в разделе пример приложения [WORDPAD](../../top/visual-cpp-samples.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
  
 `CRichEditDoc`  
  
## Требования  
 **Header:**  afxrich.h  
  
## См. также  
 [Образец WORDPAD MFC](../../top/visual-cpp-samples.md)   
 [COleServerDoc Class](../Topic/COleServerDoc%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl Class](../Topic/CRichEditCtrl%20Class.md)