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
ms.openlocfilehash: 882c589d0d25b54650affa7fd41f916ecf6097d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327110"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Операции буфера обмена с использованием элементов управления "Rich Edit"

Приложение можно вставить содержимое буфера обмена в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью лучше всего доступных формат буфера обмена или определенный формат буфера обмена. Также можно определить в элементе управления rich edit способен ли вставка формат буфера обмена.

Можно копировать или вырезать содержимое текущего выделения с помощью [копирования](../mfc/reference/cricheditctrl-class.md#copy) или [Вырезать](../mfc/reference/cricheditctrl-class.md#cut) функция-член. Аналогичным образом, можно вставить содержимое буфера обмена в элементе управления rich edit, используя [вставьте](../mfc/reference/cricheditctrl-class.md#paste) функция-член. Элемент управления Вставляет первый доступных формат, распознаваемый, который предположительно является наиболее описательные форматом.

Чтобы вставить определенный формат буфера обмена, можно использовать [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) функция-член. Эта функция полезна для приложений с помощью Специальная вставка команды, которая позволяет пользователю выбрать формат буфера обмена. Можно использовать [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) функция-член для определения ли данный формат распознается элементом управления.

Можно также использовать `CanPaste` для определения, распознается ли все доступные формат буфера обмена в элементе управления rich edit. Эта функция полезна в `OnInitMenuPopup` обработчика. Приложение может включить или серый его команда "Вставить" в зависимости от того, является ли элемент управления можно вставить любом доступном формате.

Два формата буфера обмена форматированным редактированием элементы управления register: текст в формате и формате, который называется RichEdit текста и объектов. Приложение можно зарегистрировать эти форматы с помощью [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции, указав **CF_RTF** и **CF_RETEXTOBJ** значения.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
