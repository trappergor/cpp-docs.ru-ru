---
title: "CRichEditCntrItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditCntrItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCntrItem class"
  - "OLE items, in rich edit views"
  - "элементы управления Rich Edit, OLE items"
  - "элементы управления Rich Edit, использование"
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditCntrItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) предоставляет функциональные возможности управления расширенного редактирования в контексте архитектуры представления документов MFC.  
  
## Синтаксис  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditCntrItem::CRichEditCntrItem](../Topic/CRichEditCntrItem::CRichEditCntrItem.md)|Создает объект `CRichEditCntrItem`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditCntrItem::SyncToRichEditObject](../Topic/CRichEditCntrItem::SyncToRichEditObject.md)|Активировать элемент как другой тип.|  
  
## Заметки  
 Элемент управления" окно "расширенного редактирования, в котором пользователь может вводить и редактирования текста.  Текст можно присвоить символ и форматирование абзаца, и может включать внедренные объект OLE.  Управления расширенного редактирования предоставляют программный интерфейс для форматирования текста.  Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для операций форматирования, доступным для пользователя.  
  
 `CRichEditView` поддерживает характерные текст и форматирование текста.  Клиента OLE `CRichEditDoc` ведет список элементов, которые в представлении.  `CRichEditCntrItem` предоставляет доступ к элементу OLE контейнер\- на стороне клиента.  
  
 Это общее \(элемент управления Windows и, следовательно, [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) и связанные классы\) доступны только для программ, выполняемых в рамках версии 3.51 в Windows 95 и Windows NT \/98 и более поздних версий.  
  
 Пример элементов контейнера расширенного редактирования использования в приложении MFC см. в разделе пример приложения [WORDPAD](../../top/visual-cpp-samples.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## Требования  
 **Header:**  afxrich.h  
  
## См. также  
 [Образец WORDPAD MFC](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)