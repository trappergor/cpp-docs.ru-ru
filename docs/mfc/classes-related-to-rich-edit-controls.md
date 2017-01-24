---
title: "Классы, связанные с элементами управления &quot;Rich Edit&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], связанные с элементами управления редактированием с форматированием"
  - "CRichEditCtrl - класс, связанные классы"
  - "CRichEditCtrlItem класс и CRichEditCtrl"
  - "CRichEditDoc - класс, Элементы управления редактированием с форматированием"
  - "CRichEditView - класс, и CRichEditCtrl"
  - "элементы управления Rich Edit, и CRichEditDoc"
  - "элементы управления Rich Edit, и CRichEditItem"
  - "элементы управления Rich Edit, и CRichEditView"
  - "элементы управления Rich Edit, классы, связанные с"
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы, связанные с элементами управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) классы предоставляют функции управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) в контексте архитектуры документов и представлений MFC.  `CRichEditView` поддерживает текст и форматирование характерные текста.  `CRichEditDoc` ведет список элементов OLE клиента, в представлении.  `CRichEditCntrItem` предоставляет доступ контейнер\- стороны к элементу OLE клиента.  Для изменения содержимого `CRichEditView`, используйте функцию [CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md) для получения основных управление расширенного редактирования.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)