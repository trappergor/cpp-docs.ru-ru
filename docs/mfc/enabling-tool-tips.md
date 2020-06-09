---
title: Включение всплывающих подсказок
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: bdd5c54f9174c42e17db0be7e13ea31acfea2dcf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615718"
---
# <a name="enabling-tool-tips"></a>Включение всплывающих подсказок

Можно включить поддержку всплывающих подсказок для дочерних элементов управления окна (таких как элементы управления в представлении формы или диалоговом окне).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Включение всплывающих подсказок для дочерних элементов управления окна

1. Вызовите `EnableToolTips` для окна, для которого необходимо предоставить подсказки.

1. Укажите строку для каждого элемента управления в обработчике [уведомлений TTN_NEEDTEXT](handling-ttn-needtext-notification-for-tool-tips.md) . Обработчик находится в схеме сообщений окна, содержащего дочерние элементы управления (например, класс представления формы). Этот обработчик должен вызвать функцию, которая идентифицирует элемент управления и задает **псзтекст** для указания текста, используемого элементом управления "Подсказка".

## <a name="see-also"></a>См. также раздел

[Всплывающие подсказки в Windows, не являющиеся производными CFrameWnd](tool-tips-in-windows-not-derived-from-cframewnd.md)
