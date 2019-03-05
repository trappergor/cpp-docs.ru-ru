---
title: Включение всплывающих подсказок
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 892ed76ef7e021544505600110cd2569d6078312
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285949"
---
# <a name="enabling-tool-tips"></a>Включение всплывающих подсказок

Вы можете включить поддержку в виде подсказок средство для дочерних элементов управления окна (например, элементы управления в формы, представления или диалоговом окне).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Чтобы включить всплывающие подсказки для дочерних элементов управления окна

1. Вызовите `EnableToolTips` для окна, для которого вы хотите предоставить всплывающие подсказки.

1. Укажите строку для каждого элемента управления в вашей [уведомления TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) обработчика. Обработчику не в схеме сообщений окна, которое содержит дочерние элементы управления (например, классу формы представления). Этот обработчик следует вызвать функцию, который определяет элемент управления и задает **pszText** можно указать текст, используемый элементом управления всплывающей подсказки.

## <a name="see-also"></a>См. также

[Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
