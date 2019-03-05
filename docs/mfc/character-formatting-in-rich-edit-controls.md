---
title: Форматирование знаков с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: a7467f9cd6a14dc6dfc2c03b6eb35f71802454fb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268646"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Форматирование знаков с использованием элементов управления "Rich Edit"

Можно использовать функции-члены элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования символов и получить сведения о форматировании. Для символов можно указать шрифт, размер, цвет и эффекты, например полужирный шрифт, курсив и защищены.

Можно применить форматирование символов с помощью [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) и [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) функций-членов. Чтобы определить текущий символ форматирование для выделенного текста, используйте [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) функция-член. [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) структура будет использована в эти функции-члены для указания атрибутов символов. Один из важные члены **CHARFORMAT** — **dwMask**. В `SetSelectionCharFormat` и `SetWordCharFormat`, **dwMask** указывает, какие атрибуты символ установит этим вызовом функции. `GetSelectionCharFormat` Представляет атрибуты первого символа в выделенном фрагменте; **dwMask** указывает атрибуты, которые они единообразны во всем выделения.

Можно также получить и «по умолчанию форматирование,» это форматирование, применяемое к любой впоследствии вставленные символы. Например если приложение устанавливает символ по умолчанию форматирование будут выводиться полужирным шрифтом, а затем вводе символа, этот символ имеет полужирное начертание. Чтобы получить и форматирование по умолчанию, используйте [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) и [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) функций-членов.

Атрибут «защищенной» символ не изменяет внешний вид текста. Если пользователь пытается изменить защищенный текст, в элементе управления rich edit отправляет своему родительскому окну **EN_PROTECTED** сообщение уведомления, позволяя родительского окна, можно разрешить или запретить изменение. Чтобы получить это сообщение уведомления, необходимо включить его с помощью [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) функция-член. Дополнительные сведения о маску события, см. в разделе [уведомления от изменить элемент управления форматированием](../mfc/notifications-from-a-rich-edit-control.md)далее в этом разделе.

Цвет переднего плана является атрибутом символа, но цвет фона является свойством элемента управления форматированным редактированием. Чтобы задать цвет фона, используйте [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) функция-член.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
