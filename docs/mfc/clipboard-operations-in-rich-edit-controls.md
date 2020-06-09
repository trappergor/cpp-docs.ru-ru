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
ms.openlocfilehash: 3dea112ed32ae618991f6ff5f05823bd5be001b6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624859"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Операции буфера обмена с использованием элементов управления "Rich Edit"

Приложение может вставить содержимое буфера обмена в форматируемый элемент управления ([CRichEditCtrl](reference/cricheditctrl-class.md)) с помощью наиболее доступного формата буфера обмена или конкретного формата буфера обмена. Кроме того, можно определить, может ли элемент управления с расширенным редактированием вставлять формат буфера обмена.

Содержимое текущего выделения можно скопировать или вырезать с помощью функции члена [Копировать](reference/cricheditctrl-class.md#copy) или [Вырезать](reference/cricheditctrl-class.md#cut) . Аналогичным образом можно вставить содержимое буфера обмена в форматируемый элемент управления с помощью функции-члена [Вставить](reference/cricheditctrl-class.md#paste) . Элемент управления вставит первый доступный формат, который он распознает, и, вероятно, является наиболее описательным форматом.

Чтобы вставить конкретный формат буфера обмена, можно использовать функцию-член [PasteSpecial](reference/cricheditctrl-class.md#pastespecial) . Эта функция полезна для приложений с командой Специальная вставка, которая позволяет пользователю выбрать формат буфера обмена. Функцию-член [канпасте](reference/cricheditctrl-class.md#canpaste) можно использовать для определения того, распознается ли данный формат элементом управления.

Можно также использовать `CanPaste` , чтобы определить, распознается ли любой доступный формат буфера обмена элементом управления Rich Edit. Эта функция полезна в `OnInitMenuPopup` обработчике. В зависимости от того, может ли элемент управления вставлять любой доступный формат, в приложении может быть включена или серая команда вставки.

Элементы управления Rich Edit регистрируют два формата буфера обмена: форматированный текст и формат с именем текст и объекты RichEdit. Приложение может зарегистрировать эти форматы с помощью функции [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) , указав значения **CF_RTF** и **CF_RETEXTOBJ** .

## <a name="see-also"></a>См. также раздел

[Использование CRichEditCtrl](using-cricheditctrl.md)<br/>
[Элементы управления](controls-mfc.md)
