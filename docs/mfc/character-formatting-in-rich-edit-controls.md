---
title: "Форматирование знаков в элементы управления Rich Edit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93bb2cda113a56276ad54edb5ccdb6c9d430ed06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="character-formatting-in-rich-edit-controls"></a>Форматирование знаков с использованием элементов управления "Rich Edit"
Можно использовать функции-члены элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования символов и получить сведения о форматировании. Для символов можно указать шрифта, размера, цвета и эффекты, такие как полужирный, курсив и protected.  
  
 Можно применить форматирование символов с помощью [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) и [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) функции-члены. Чтобы определить текущий символ форматирование для выделенного текста, используйте [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) функции-члена. [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) использовать структуру с такие функции-члены для указания атрибутов символов. Одно из важные члены **CHARFORMAT** — **dwMask**. В `SetSelectionCharFormat` и `SetWordCharFormat`, **dwMask** указывает, какие атрибуты символов установит этот вызов функции. `GetSelectionCharFormat`Выводит атрибуты первого символа в выделенном фрагменте; **dwMask** указывает атрибуты, которые они единообразны во всем выделение.  
  
 Можно также получить и задать «по умолчанию форматирование символов,» это форматирование, применяемое к любой впоследствии вставленные символы. Например если приложение задает символ по умолчанию форматирование будут выводиться полужирным шрифтом, а затем пользователем символ, символ выделено полужирным шрифтом. Чтобы получить и форматирование по умолчанию, используйте [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) и [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) функции-члены.  
  
 Атрибут «защищенные» знаков не изменяет внешний вид текста. Если пользователь пытается изменить защищенный текст, в элементе управления rich edit отправляет родительского окна **EN_PROTECTED** сообщение уведомления, позволяя родительского окна разрешить или запретить изменение. Чтобы получить это сообщение уведомления, необходимо включить его с помощью [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) функции-члена. Дополнительные сведения о маску события. в разделе [уведомления от элемент управления Rich Edit](../mfc/notifications-from-a-rich-edit-control.md)далее в этом разделе.  
  
 Цвет переднего плана является атрибутом символа, но цвет фона является свойством элемента управления rich edit. Чтобы задать цвет фона, используйте [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

