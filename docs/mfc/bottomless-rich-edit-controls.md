---
title: Элементы управления "Rich Edit" "без дна"
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 4affdbeed723ea83beda785116dc4c45771073b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509151"
---
# <a name="bottomless-rich-edit-controls"></a>Элементы управления "Rich Edit" "без дна"

Приложение может изменить размер элемента управления Rich Edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) по мере необходимости, чтобы он всегда был таким же, как и его содержимое. Форматированный элемент управления "поле ввода" поддерживает эту функцию "без нижнего уровня", отправляя родительское окно сообщение уведомления [EN_REQUESTRESIZE](/windows/win32/Controls/en-requestresize) при изменении размера его содержимого.

При обработке сообщения уведомления **EN_REQUESTRESIZE** приложение должно изменить размер элемента управления до размеров в указанной структуре [рекресизе](/windows/win32/api/richedit/ns-richedit-reqresize) . Приложение также может перемещать любые сведения, расположенные рядом с элементом управления, чтобы обеспечить изменение высоты элемента управления. Чтобы изменить размер элемента управления, можно использовать `CWnd` функцию [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Вы можете принудительно применить неформатированный элемент управления "поле с небольшими значениями" для отправки сообщения уведомления **EN_REQUESTRESIZE** с помощью функции-члена [рекуестресизе](../mfc/reference/cricheditctrl-class.md#requestresize) . Это сообщение может быть полезно в обработчике [OnSize](../mfc/reference/cwnd-class.md#onsize) .

Чтобы получить сообщения уведомления **EN_REQUESTRESIZE** , необходимо включить уведомление с помощью `SetEventMask` функции члена.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
