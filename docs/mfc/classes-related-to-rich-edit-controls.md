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
ms.openlocfilehash: 584649a2bb2d9a118e390aebf9f7411c3123b1a3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620716"
---
# <a name="classes-related-to-rich-edit-controls"></a>Классы, связанные с элементами управления "Rich Edit"

Классы [CRichEditView](reference/cricheditview-class.md), [CRichEditDoc](reference/cricheditdoc-class.md)и [кричедиткнтритем](reference/cricheditcntritem-class.md) предоставляют функциональные возможности элемента управления Rich Edit ([CRichEditCtrl](reference/cricheditctrl-class.md)) в контексте архитектуры документов и представлений MFC. `CRichEditView`поддерживает текстовую характеристику текста и форматирования текста. `CRichEditDoc`поддерживает список элементов OLE, которые находятся в представлении. `CRichEditCntrItem`предоставляет доступ на стороне контейнера к элементу OLE-клиента. Чтобы изменить содержимое `CRichEditView` , используйте [CRichEditView:: жетричедитктрл](reference/cricheditview-class.md#getricheditctrl) для доступа к базовому элементу управления Rich Edit.

## <a name="see-also"></a>См. также раздел

[Использование CRichEditCtrl](using-cricheditctrl.md)<br/>
[Элементы управления](controls-mfc.md)
