---
title: Текущее выделение в элементе управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: 43a68d63f7888d762eee031196453eb156ecf105
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508777"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Текущее выделение в элементе управления "Rich Edit"

Пользователь может выбрать текст в элементе управления Rich Edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью мыши или клавиатуры. Текущий выделенный фрагмент — это диапазон выбранных символов или позиция точки вставки, если ни одна из символов не выбрана. Приложение может получить сведения о текущем выделении, установить текущее выделение, определить, когда текущий выбор изменится, а также показать или скрыть выделение выделения.

Чтобы определить текущее выделение в элементе управления Rich Edit, используйте функцию-член [жетсел](../mfc/reference/cricheditctrl-class.md#getsel) . Чтобы задать текущее выделение, используйте функцию члена [сетсел](../mfc/reference/cricheditctrl-class.md#setsel) . Структура [чарранже](/windows/win32/api/richedit/ns-richedit-charrange) используется с этими функциями для указания диапазона символов. Чтобы получить сведения о содержимом текущего выделения, можно использовать функцию члена [жетселектионтипе](../mfc/reference/cricheditctrl-class.md#getselectiontype) .

По умолчанию элемент управления с расширенным редактированием показывает и скрывает выделение выделения при получении и потере фокуса. Выделение выделения можно показать или скрыть в любое время с помощью функции члена [хидеселектион](../mfc/reference/cricheditctrl-class.md#hideselection) . Например, приложение может предоставить диалоговое окно поиска для поиска текста в элементе управления Rich Edit. Приложение может выбрать соответствующий текст, не закрывая диалоговое окно. в этом случае для выделения `HideSelection` выбранного фрагмента необходимо использовать.

Чтобы получить выделенный текст в элементе управления Rich Edit, используйте функцию-член [жетселтекст](../mfc/reference/cricheditctrl-class.md#getseltext) . Текст копируется в указанный массив символов. Необходимо убедиться, что массив достаточно велик, чтобы вместить выделенный текст, а также завершающий нуль-символ.

Можно выполнить поиск строки в элементе управления Rich Edit с помощью функции-члена [строки FindText](../mfc/reference/cricheditctrl-class.md#findtext) . Структура [финдтекстекс](/windows/win32/api/richedit/ns-richedit-findtextexw) , используемая с этой функцией, задает текстовый диапазон для поиска и искомую строку. Можно также указать такие параметры, как при поиске с учетом регистра.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
