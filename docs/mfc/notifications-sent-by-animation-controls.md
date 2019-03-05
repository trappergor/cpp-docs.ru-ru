---
title: Уведомления, отправленные элементами управления "Анимация"
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 2a736e4315091b1b26daceb4fe0ce9672ab33ff6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281269"
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"

Элемент управления анимации ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) отправляет два разных типа сообщений уведомления. Уведомления отправляются в виде [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщений.

[ACN_START](/windows/desktop/Controls/acn-start) сообщение отправляется в том случае, когда управления анимация начала проигрываться клипа. [ACN_STOP](/windows/desktop/Controls/acn-stop) сообщение отправляется в том случае, если отображается этот элемент управления имеет завершения или остановки воспроизведения клипа.

## <a name="see-also"></a>См. также

[Использование CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
