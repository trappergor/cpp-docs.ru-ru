---
title: Обработка отраженных сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 8907b432cf4dabad33c0925b841f65dfc57c6295
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620139"
---
# <a name="handling-reflected-messages"></a>Обработка отраженных сообщений

Отражение сообщений позволяет управлять сообщениями для таких элементов управления, как **WM_CTLCOLOR**, **WM_COMMAND**и **WM_NOTIFY**, внутри самого элемента управления. Это делает элемент управления более самодостаточным и переносимым. Механизм работает с обычными элементами управления Windows, а также с элементами управления ActiveX (ранее называемыми элементами управления OLE).

Отражение сообщений позволяет `CWnd` более быстро использовать производные классы. Отражение сообщений работает через [CWnd:: ончилднотифи](reference/cwnd-class.md#onchildnotify)с использованием специальных **ON_XXX_REFLECT** записей схемы сообщений: например **ON_CTLCOLOR_REFLECT** и **ON_CONTROL_REFLECT**. [Техническое примечание 62](tn062-message-reflection-for-windows-controls.md) . более подробное описание отражения сообщений.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Дополнительные сведения о отражении сообщений](tn062-message-reflection-for-windows-controls.md)

- [Реализация отражения сообщений для общего элемента управления](tn062-message-reflection-for-windows-controls.md)

- [Реализация отражения сообщений для элемента управления ActiveX](mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>См. также раздел

[Объявление функций обработчика сообщений](declaring-message-handler-functions.md)
