---
title: Включение всплывающих подсказок | Документы Microsoft
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
ms.openlocfilehash: 598583360eca2a65a5352fc9d284d8d359ac021c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-tool-tips"></a>Включение всплывающих подсказок
Можно включить поддержку совет средство для дочерних элементов управления окна (например, элементы управления на форму представления или диалогового окна поле).  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Включение всплывающих подсказок для дочерних элементов управления окна  
  
1.  Вызовите `EnableToolTips` для окна, для которого вы хотите предоставить всплывающие подсказки.  
  
2.  Укажите строку для каждого элемента управления в вашей [уведомления TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) обработчика. Обработчик находится в схеме сообщений окна, содержащую дочерние элементы (например, классу формы представления). Этот обработчик должен вызывать функции, определяет элемент управления и задает **pszText** для указания текста, используемый элементом управления всплывающей подсказки.  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

