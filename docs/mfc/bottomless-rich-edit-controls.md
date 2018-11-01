---
title: Элементы управления "Rich Edit" "без дна"
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 1c5578181b580ddb07b69f5fd2e91aea4b85a72b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624876"
---
# <a name="bottomless-rich-edit-controls"></a>Элементы управления "Rich Edit" "без дна"

Приложения можно изменить размер элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) при необходимости, так как это всегда совпадает с размером его содержимого. Элемент управления форматированным редактированием поддерживает данную так называемые «без дна» функцию, отправив своему родительскому окну [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) уведомление при каждом изменении размера его содержимое.

При обработке **EN_REQUESTRESIZE** сообщение уведомления, приложения должны изменяться размеры элемента управления к измерениям в указанном [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) структуры. Приложение также может перемещать данные рядом с элементом управления для размещения элемента управления изменение высоты. Чтобы изменить размер элемента управления, можно использовать `CWnd` функция [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Вы можете принудительно элементе управления "без дна rich edit" для отправки **EN_REQUESTRESIZE** сообщение уведомления с помощью [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) функция-член. Это сообщение может быть полезно в [OnSize](../mfc/reference/cwnd-class.md#onsize) обработчика.

Для получения **EN_REQUESTRESIZE** сообщений уведомлений, необходимо включить уведомления с помощью `SetEventMask` функция-член.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

