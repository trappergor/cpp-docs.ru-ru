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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238313"
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"

Элемент управления анимации ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) отправляет два разных типа сообщений уведомления. Уведомления отправляются в виде [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщений.

[ACN_START](/windows/desktop/Controls/acn-start) сообщение отправляется в том случае, когда управления анимация начала проигрываться клипа. [ACN_STOP](/windows/desktop/Controls/acn-stop) сообщение отправляется в том случае, если отображается этот элемент управления имеет завершения или остановки воспроизведения клипа.

## <a name="see-also"></a>См. также

[Использование CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
