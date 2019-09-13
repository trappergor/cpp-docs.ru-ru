---
title: Операции буфера обмена с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: e232010b443ace245844f1c28649477cccc8e9e4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508970"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Операции буфера обмена с использованием элементов управления "Rich Edit"

Приложение может вставить содержимое буфера обмена в форматируемый элемент управления ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью наиболее доступного формата буфера обмена или конкретного формата буфера обмена. Кроме того, можно определить, может ли элемент управления с расширенным редактированием вставлять формат буфера обмена.

Содержимое текущего выделения можно скопировать или вырезать с помощью функции члена [Копировать](../mfc/reference/cricheditctrl-class.md#copy) или [Вырезать](../mfc/reference/cricheditctrl-class.md#cut) . Аналогичным образом можно вставить содержимое буфера обмена в форматируемый элемент управления с помощью функции-члена [Вставить](../mfc/reference/cricheditctrl-class.md#paste) . Элемент управления вставит первый доступный формат, который он распознает, и, вероятно, является наиболее описательным форматом.

Чтобы вставить конкретный формат буфера обмена, можно использовать функцию-член [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) . Эта функция полезна для приложений с командой Специальная вставка, которая позволяет пользователю выбрать формат буфера обмена. Функцию-член [канпасте](../mfc/reference/cricheditctrl-class.md#canpaste) можно использовать для определения того, распознается ли данный формат элементом управления.

Можно также использовать `CanPaste` , чтобы определить, распознается ли любой доступный формат буфера обмена элементом управления Rich Edit. Эта функция полезна в `OnInitMenuPopup` обработчике. В зависимости от того, может ли элемент управления вставлять любой доступный формат, в приложении может быть включена или серая команда вставки.

Элементы управления Rich Edit регистрируют два формата буфера обмена: форматированный текст и формат с именем текст и объекты RichEdit. Приложение может зарегистрировать эти форматы с помощью функции [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) , указав значения **CF_RTF** и **CF_RETEXTOBJ** .

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
