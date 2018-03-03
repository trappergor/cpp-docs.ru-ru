---
title: "Операции буфера обмена Rich Edit элементы управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec468b1f763e2f855f25fd8808d83605fb10673a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Операции буфера обмена с использованием элементов управления "Rich Edit"
Приложение можно вставить содержимое буфера обмена в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью лучше всего доступных формат буфера обмена или определенный формат буфера обмена. Также можно определить в элементе управления rich edit способно ли вставка формат буфера обмена.  
  
 Можно копировать или вырезать содержимое текущего выделенного фрагмента с помощью [копирования](../mfc/reference/cricheditctrl-class.md#copy) или [Вырезать](../mfc/reference/cricheditctrl-class.md#cut) функции-члена. Аналогичным образом, можно вставить содержимое буфера обмена в элементе управления rich edit с помощью [вставьте](../mfc/reference/cricheditctrl-class.md#paste) функции-члена. Элемент управления Вставляет первый доступных формат, распознаваемый, который предположительно является наиболее описательные форматом.  
  
 Чтобы вставить определенный формат буфера обмена, можно использовать [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) функции-члена. Эта функция полезна для приложений с помощью команды Специальная вставка, позволяющий пользователю выбрать формат буфера обмена. Можно использовать [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) функции-члена для определения ли данный формат распознается элементом управления.  
  
 Можно также использовать `CanPaste` для определения, распознается ли любом доступном формате буфера обмена в элементе управления rich edit. Эта функция полезна в `OnInitMenuPopup` обработчика. Приложение может включить или серого цвета, его команда "Вставить" в зависимости от того, является ли элемент управления можно вставить в любом доступном формате.  
  
 Два формата буфера обмена форматируемого элементы управления регистра: текст в формате и формате, который называется RichEdit текст и объекты. Приложение может зарегистрировать эти форматы с помощью [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции, указав **CF_RTF** и **CF_RETEXTOBJ** значения.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

