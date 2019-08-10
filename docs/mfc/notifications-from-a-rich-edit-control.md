---
title: Уведомления из элемента управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: bc4c027ff26df89539b22c6d04f1d1dc95fc459a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916405"
---
# <a name="notifications-from-a-rich-edit-control"></a>Уведомления из элемента управления "Rich Edit"

Сообщения уведомления сообщают о событиях, затрагивающих элемент управления Rich Edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Они могут обрабатываться родительским окном или с помощью отражения сообщений самим элементом управления "поле ввода". Элементы управления Rich Edit поддерживают все сообщения уведомлений, используемые с элементами управления "поле ввода", а также несколько дополнительных. Вы можете определить, какие сообщения уведомления отправляются элементом управления с расширенным редактированием, установив его "маску событий".

Чтобы задать маску событий для элемента управления расширенного редактирования, используйте функцию-член [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) . Можно получить текущую маску события для элемента управления Rich Edit с помощью функции-члена [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) .

В следующих абзацах перечислены несколько конкретных уведомлений и их использование.

- EN_MSGFILTER обработка уведомлений EN_MSGFILTER позволяет классу, элементу управления Rich Edit или его родительскому окну, фильтровать все входные данные клавиатуры и мыши в элементе управления. Обработчик может предотвратить обработку сообщения клавиатуры или мыши или изменить сообщение, изменив указанную структуру [мсгфилтер](/windows/desktop/api/richedit/ns-richedit-msgfilter) .

- EN_PROTECTED обрабатывает сообщение уведомления EN_PROTECTED, чтобы определить, когда пользователь пытается изменить защищенный текст. Чтобы пометить диапазон текста как защищенный, можно задать защищенный символ. Дополнительные сведения см. [в разделе Форматирование символов в элементах управления Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES можно разрешить пользователю удалять файлы в элементе управления Rich Edit, обрабатывая сообщение уведомления EN_DROPFILES. Указанная структура [ендропфилес](/windows/desktop/api/richedit/ns-richedit-endropfiles) содержит сведения об удаляемых файлах.

- EN_SELCHANGE приложение может обнаружить, когда текущее выделение изменится, обрабатывая сообщение уведомления EN_SELCHANGE. В сообщении уведомления указана структура [селчанже](/windows/desktop/api/richedit/ns-richedit-selchange) , содержащая сведения о новом выделенном фрагменте.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
