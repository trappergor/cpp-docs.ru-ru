---
title: Уведомления, отправленные элементами управления "Анимация"
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: e9e5b94736de44d5cfeef81f5b78a759df3b8aa0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619910"
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"

Элемент управления анимации ([CAnimateCtrl](reference/canimatectrl-class.md)) отправляет два разных типа сообщений уведомления. Уведомления отправляются в виде [WM_COMMAND](/windows/win32/menurc/wm-command) сообщений.

[ACN_START](/windows/win32/Controls/acn-start) сообщение отправляется, когда элемент управления анимации начинает воспроизводить клип. [ACN_STOP](/windows/win32/Controls/acn-stop) сообщение отправляется при завершении или остановке воспроизведения клипа элементом управления анимации.

## <a name="see-also"></a>См. также раздел

[Использование CAnimateCtrl](using-canimatectrl.md)<br/>
[Элементы управления](controls-mfc.md)
