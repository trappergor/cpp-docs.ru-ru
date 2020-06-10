---
title: Форматирование знаков с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: 0b9d925b6ba3157177b7012d1e303ef7b7ddab46
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624937"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Форматирование знаков с использованием элементов управления "Rich Edit"

Функции-члены элемента управления Rich Edit ([CRichEditCtrl](reference/cricheditctrl-class.md)) можно использовать для форматирования символов и получения сведений о форматировании. Для символов можно указать гарнитуру, размер, цвет и эффекты, такие как полужирный, курсив и защищенный.

Форматирование символов можно применить с помощью функций члена [сетселектиончарформат](reference/cricheditctrl-class.md#setselectioncharformat) и [сетвордчарформат](reference/cricheditctrl-class.md#setwordcharformat) . Чтобы определить текущее форматирование символов для выделенного текста, используйте функцию члена [жетселектиончарформат](reference/cricheditctrl-class.md#getselectioncharformat) . Структура [чарформат](/windows/win32/api/richedit/ns-richedit-charformata) используется с этими функциями-членами для указания атрибутов символов. Одним из важных членов **чарформат** является **двмаск**. В `SetSelectionCharFormat` и `SetWordCharFormat` **двмаск** указывает, какие символьные атрибуты будут заданы этим вызовом функции. `GetSelectionCharFormat`сообщает об атрибутах первого символа в выделенном фрагменте. **двмаск** задает атрибуты, согласованные по всему выбору.

Можно также получить и установить параметр «форматирование символов по умолчанию», который применяется к вставленным символам. Например, если приложение устанавливает форматирование символов по умолчанию полужирным, а пользователь вводит символ, этот символ выделяется полужирным шрифтом. Чтобы получить и установить форматирование символов по умолчанию, используйте функции члена [жетдефаултчарформат](reference/cricheditctrl-class.md#getdefaultcharformat) и [сетдефаултчарформат](reference/cricheditctrl-class.md#setdefaultcharformat) .

Атрибут «protected» не изменяет внешний вид текста. Если пользователь пытается изменить защищенный текст, то элемент управления с расширенным редактированием отправляет родительскому окну сообщение **EN_PROTECTED** уведомления, позволяя родительскому окну разрешать или запрещать изменение. Чтобы получить это сообщение уведомления, необходимо включить его с помощью функции члена [SetEventMask](reference/cricheditctrl-class.md#seteventmask) . Дополнительные сведения о маске событий см. в разделе [уведомления из элемента управления Rich Edit](notifications-from-a-rich-edit-control.md)далее в этом разделе.

Цвет переднего плана — это символьный атрибут, но цвет фона является свойством элемента управления Rich Edit. Чтобы задать цвет фона, используйте функцию члена [сетбаккграундколор](reference/cricheditctrl-class.md#setbackgroundcolor) .

## <a name="see-also"></a>См. также раздел

[Использование CRichEditCtrl](using-cricheditctrl.md)<br/>
[Элементы управления](controls-mfc.md)
