---
title: Операции буфера обмена Rich Edit элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb207b31da27041ee777277e7e76502789402ab7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216234"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Операции буфера обмена с использованием элементов управления "Rich Edit"
Приложение можно вставить содержимое буфера обмена в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью лучше всего доступных формат буфера обмена или определенный формат буфера обмена. Также можно определить в элементе управления rich edit способен ли вставка формат буфера обмена.  
  
 Можно копировать или вырезать содержимое текущего выделения с помощью [копирования](../mfc/reference/cricheditctrl-class.md#copy) или [Вырезать](../mfc/reference/cricheditctrl-class.md#cut) функция-член. Аналогичным образом, можно вставить содержимое буфера обмена в элементе управления rich edit, используя [вставьте](../mfc/reference/cricheditctrl-class.md#paste) функция-член. Элемент управления Вставляет первый доступных формат, распознаваемый, который предположительно является наиболее описательные форматом.  
  
 Чтобы вставить определенный формат буфера обмена, можно использовать [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) функция-член. Эта функция полезна для приложений с помощью Специальная вставка команды, которая позволяет пользователю выбрать формат буфера обмена. Можно использовать [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) функция-член для определения ли данный формат распознается элементом управления.  
  
 Можно также использовать `CanPaste` для определения, распознается ли все доступные формат буфера обмена в элементе управления rich edit. Эта функция полезна в `OnInitMenuPopup` обработчика. Приложение может включить или серый его команда "Вставить" в зависимости от того, является ли элемент управления можно вставить любом доступном формате.  
  
 Два формата буфера обмена форматированным редактированием элементы управления register: текст в формате и формате, который называется RichEdit текста и объектов. Приложение можно зарегистрировать эти форматы с помощью [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции, указав **CF_RTF** и **CF_RETEXTOBJ** значения.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

