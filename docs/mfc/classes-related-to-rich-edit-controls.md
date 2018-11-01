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
ms.openlocfilehash: 92134d0bd4d02bff7aeadd5e9ca7438c61de3bec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586164"
---
# <a name="classes-related-to-rich-edit-controls"></a>Классы, связанные с элементами управления "Rich Edit"

[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) классы предоставляют функциональность элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) в контексте архитектуры документов или представлений MFC. `CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` поддерживает список клиентских элементов управления OLE, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к элемент клиента OLE. Чтобы изменить содержимое `CRichEditView`, использовать [CRichEditView::GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) для доступа к основной элемент управления rich edit.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

