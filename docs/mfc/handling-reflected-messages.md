---
title: Обработка отраженных сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99fc9c30ea85ba3f94fa811464f023da0eeea37e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438682"
---
# <a name="handling-reflected-messages"></a>Обработка отраженных сообщений

Отражение позволяет обрабатывать сообщения для элемента управления, такие как сообщения **WM_CTLCOLOR**, **WM_COMMAND**, и **WM_NOTIFY**, внутри себя. Это делает элемент управления более автономной и переносной. Этот механизм работает с помощью стандартных элементов управления Windows, а также с элементами управления ActiveX (ранее называвшихся элементов управления OLE).

Сообщение, отражение позволяет повторно использовать ваши `CWnd`-производные классы более эффективно. Сообщения works отражение через [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), с помощью специальных **ON_XXX_REFLECT** записей карты сообщений: например, **ON_CTLCOLOR_REFLECT** и **ON_CONTROL_REFLECT**. [Технические заметки 62](../mfc/tn062-message-reflection-for-windows-controls.md) объясняет отражение сообщений более подробно.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Дополнительные сведения об отражении сообщения](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Реализовать отражение сообщений для общего элемента управления](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Реализовать отражение сообщений для элемента управления ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>См. также

[Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
