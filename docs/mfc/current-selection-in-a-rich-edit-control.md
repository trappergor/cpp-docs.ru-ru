---
title: Текущее выделение в элементе управления Rich Edit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5870c7c3352a53d85bdd15020a1e7f535ef6efc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403673"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Текущее выделение в элементе управления "Rich Edit"

Пользователь может выбрать текст в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью мыши или клавиатуры. Выделенный фрагмент находится в диапазоне выбранных символов или положение курсора, если никакие символы не выбраны. Приложение может получить сведения о выделенном, задать текущий выбор, определить, когда изменения текущего выделения и Показать или скрыть выделение выделить.

Чтобы определить текущее выделение в элементе управления rich edit, используйте [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) функция-член. Чтобы задать текущее выделение, используйте [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) функция-член. [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) структура используется с этими функциями для указания диапазона символов. Чтобы получить сведения о содержимом текущего выделенного фрагмента, можно использовать [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) функция-член.

По умолчанию элемента управления форматированным редактированием показано и скрывает выделение выбора, когда он получает и теряет фокус. Можно отобразить или скрыть выделение выбора в любое время с помощью [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) функция-член. Например приложение может предоставлять диалоговое окно поиска для поиска текста в элементе управления rich edit. Приложение может выбрать соответствующий текст без закрытия диалогового окна, в этом случае необходимо использовать `HideSelection` выделения.

Чтобы получить выделенный текст в элементе управления rich edit, используйте [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) функция-член. Текст копируется в указанный массив символов. Необходимо убедиться, что массив имеет недостаточно велик для хранения, выделенный текст, а также конечного нуль-символа.

Можно найти строки в элементе управления rich edit, с помощью [FindText](../mfc/reference/cricheditctrl-class.md#findtext) функция-член [FINDTEXTEX](/windows/desktop/api/richedit/ns-richedit-_findtextexa) структура, используемая с этой функцией указывает диапазон текста для поиска и строку для поиска. Можно также указать такие параметры, как при поиске учитывается регистр.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

