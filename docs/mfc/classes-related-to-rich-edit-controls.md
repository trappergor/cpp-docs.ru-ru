---
title: Классы, связанные с элементами управления "Rich Edit"
ms.date: 11/04/2016
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
ms.openlocfilehash: 349a8b5c26b7260c9af496d0f4a3a997ee753020
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258103"
---
# <a name="classes-related-to-rich-edit-controls"></a>Классы, связанные с элементами управления "Rich Edit"

[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) классы предоставляют функциональность элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) в контексте архитектуры документов или представлений MFC. `CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` поддерживает список клиентских элементов управления OLE, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к элемент клиента OLE. Чтобы изменить содержимое `CRichEditView`, использовать [CRichEditView::GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) для доступа к основной элемент управления rich edit.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
