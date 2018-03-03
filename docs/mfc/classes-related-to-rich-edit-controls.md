---
title: "Классы, связанные с элементами управления Rich Edit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8373435f1f97b6b2038e5769c853d521b906715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="classes-related-to-rich-edit-controls"></a>Классы, связанные с элементами управления "Rich Edit"
[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) классы предоставляют функциональные возможности управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) в контексте архитектуры документов или представлений MFC. `CRichEditView`Сохраняет текст и параметры форматирования текста. `CRichEditDoc`поддерживает список клиентских элементов управления OLE, в представлении. `CRichEditCntrItem`Предоставляет контейнер стороне доступ к элемент клиента OLE. Чтобы изменить содержимое `CRichEditView`, используйте [CRichEditView::GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) для доступа к базовый элемент управления rich edit.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

