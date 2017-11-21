---
title: "Текущее выделение в элементе управления Rich Edit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b41b99ca515cb91c097cb20c3ef0cd0e5dccb64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="current-selection-in-a-rich-edit-control"></a>Текущее выделение в элементе управления "Rich Edit"
Пользователь может выбрать текст в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) с помощью клавиатуры или мыши. Выделена диапазон выбранных символов или положение курсора, если символов не выбраны. Приложения можно получить сведения о текущее выделение, задать текущее выделение, определить, когда текущие изменения выбора и отображать или скрывать Выбор выделения.  
  
 Чтобы определить текущее выделение в элементе управления rich edit, используйте [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) функции-члена. Чтобы задать текущее выделение, используйте [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) функции-члена. [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) использовать структуру с этими функциями для указания диапазона символов. Чтобы получить сведения о содержимом текущего выделенного фрагмента, можно использовать [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) функции-члена.  
  
 По умолчанию элемента управления rich edit показано и скрывает выделение, когда он получает и теряет фокус. Можно отобразить или скрыть выделение в любое время с помощью [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) функции-члена. Например приложение может предоставлять диалоговое окно поиска для поиска текста в элементе управления rich edit. Приложение может выбрать соответствующий текст без закрытия диалогового окна, в этом случае необходимо использовать `HideSelection` выделения.  
  
 Чтобы получить выделенный текст в элементе управления rich edit, используйте [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) функции-члена. Текст копируется в указанный массив символов. Необходимо убедиться, что массив имеет недостаточно велик для хранения выделенный текст и завершающий нуль-символа.  
  
 Можно искать строку в элементе управления rich edit, с помощью [строки FindText](../mfc/reference/cricheditctrl-class.md#findtext) функции-члена [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) структура, используемая с помощью этой функции указывает текстовый диапазон для поиска и строку для поиска. Также можно указать такие параметры, как при поиске учитывается регистр.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

