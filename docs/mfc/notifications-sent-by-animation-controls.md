---
title: Уведомления, отправленные элементами управления анимации | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb83fe6195c01c1e9dbcc2c00e43738af9ebc8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386396"
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"

Элемент управления анимации ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) отправляет два разных типа сообщений уведомления. Уведомления отправляются в виде [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщений.

[ACN_START](/windows/desktop/Controls/acn-start) сообщение отправляется в том случае, когда управления анимация начала проигрываться клипа. [ACN_STOP](/windows/desktop/Controls/acn-stop) сообщение отправляется в том случае, если отображается этот элемент управления имеет завершения или остановки воспроизведения клипа.

## <a name="see-also"></a>См. также

[Использование CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

