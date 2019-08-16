---
title: Уведомления, отправленные элементами управления "Анимация"
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 68ede3bc55669a29eef192d38b29b8c1ab433e4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508018"
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"

Элемент управления анимации ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) отправляет два разных типа сообщений уведомления. Уведомления отправляются в виде сообщений [WM_COMMAND](/windows/win32/menurc/wm-command) .

Сообщение [ACN_START](/windows/win32/Controls/acn-start) отправляется, когда элемент управления анимации начинает воспроизводить клип. Сообщение [ACN_STOP](/windows/win32/Controls/acn-stop) отправляется при завершении или остановке воспроизведения клипа элементом управления анимации.

## <a name="see-also"></a>См. также

[Использование CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
