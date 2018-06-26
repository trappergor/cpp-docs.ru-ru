---
title: Обработка отраженных сообщений | Документы Microsoft
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
ms.openlocfilehash: 9b317f4c1b55e04f61aa0639bbd6953e5f36187a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931844"
---
# <a name="handling-reflected-messages"></a>Обработка отраженных сообщений
Отражение позволяет обрабатывать сообщения для элемента управления, такие как сообщения **WM_CTLCOLOR**, **WM_COMMAND**, и **WM_NOTIFY**, внутри себя. Это делает элемент управления более автономной и переносной. Механизм работает Общие элементы управления Windows, а также элементы управления ActiveX (ранее — элементы управления OLE).  
  
 Отражение позволяет многократно использовать сообщения вашей `CWnd`-легче производных классов. Сообщение отражения работает через [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), с помощью специальных **ON_XXX_REFLECT** записей карты сообщений: например, **ON_CTLCOLOR_REFLECT** и **ON_CONTROL_REFLECT**. [Технические примечания 62](../mfc/tn062-message-reflection-for-windows-controls.md) объясняет отражение сообщения более подробно.  
  
## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
  
-   [Дополнительные сведения о отражение сообщения](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Реализуйте отражение сообщений для стандартного элемента управления](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Реализуйте отражение сообщений для элемента управления ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>См. также  
 [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
