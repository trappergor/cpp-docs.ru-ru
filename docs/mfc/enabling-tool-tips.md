---
title: Включение всплывающих подсказок | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 968d31b49c6d2b2fe5a5f69e04f58f17de8df5a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440489"
---
# <a name="enabling-tool-tips"></a>Включение всплывающих подсказок

Вы можете включить поддержку в виде подсказок средство для дочерних элементов управления окна (например, элементы управления в формы, представления или диалоговом окне).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Чтобы включить всплывающие подсказки для дочерних элементов управления окна

1. Вызовите `EnableToolTips` для окна, для которого вы хотите предоставить всплывающие подсказки.

1. Укажите строку для каждого элемента управления в вашей [уведомления TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) обработчика. Обработчику не в схеме сообщений окна, которое содержит дочерние элементы управления (например, классу формы представления). Этот обработчик следует вызвать функцию, который определяет элемент управления и задает **pszText** можно указать текст, используемый элементом управления всплывающей подсказки.

## <a name="see-also"></a>См. также

[Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

