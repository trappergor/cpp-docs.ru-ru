---
title: "Включение всплывающих подсказок | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0555af785d75c9247eb365a03a51161441a4722a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-tool-tips"></a>Включение всплывающих подсказок
Можно включить поддержку совет средство для дочерних элементов управления окна (например, элементы управления на форму представления или диалогового окна поле).  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Включение всплывающих подсказок для дочерних элементов управления окна  
  
1.  Вызовите `EnableToolTips` для окна, для которого вы хотите предоставить всплывающие подсказки.  
  
2.  Укажите строку для каждого элемента управления в вашей [уведомления TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) обработчика. Обработчик находится в схеме сообщений окна, содержащую дочерние элементы (например, классу формы представления). Этот обработчик должен вызывать функции, определяет элемент управления и задает **pszText** для указания текста, используемый элементом управления всплывающей подсказки.  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

