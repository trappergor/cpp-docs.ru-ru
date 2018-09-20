---
title: Классы, связанные с элементами управления Rich Edit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee7b6400dcd5c91d054b31153c21008d5302bd0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401268"
---
# <a name="classes-related-to-rich-edit-controls"></a>Классы, связанные с элементами управления "Rich Edit"

[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) классы предоставляют функциональность элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) в контексте архитектуры документов или представлений MFC. `CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` поддерживает список клиентских элементов управления OLE, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к элемент клиента OLE. Чтобы изменить содержимое `CRichEditView`, использовать [CRichEditView::GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) для доступа к основной элемент управления rich edit.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

