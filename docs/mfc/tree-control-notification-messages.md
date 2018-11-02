---
title: Уведомляющие сообщения древовидного элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: e187e08f894eeac37c8ad27aea45a1c8568c8a9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508186"
---
# <a name="tree-control-notification-messages"></a>Уведомляющие сообщения древовидного элемента управления

Дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет следующие сообщения уведомления как сообщения WM_NOTIFY:

|Сообщение уведомления|Описание|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Сигнализирует о начале операции перетаскивания и вставки|
|TVN_BEGINLABELEDIT|Сигнализирует о начале редактирования метки на месте|
|TVN_BEGINRDRAG|Сигнализирует о начале операции перетаскивания и вставки, с помощью правой кнопки мыши|
|TVN_DELETEITEM|Сигнализирует о удаление этого элемента|
|TVN_ENDLABELEDIT|Сигнализирует об окончании редактирования метки|
|TVN_GETDISPINFO|Запрашивает информацию, что дерево требуется для отображения элемента|
|TVN_ITEMEXPANDED|Сообщает, что с родительским элементом списка дочерних элементов был развернут или свернут|
|TVN_ITEMEXPANDING|Показывает, будет разворачивать и сворачивать с родительским элементом списка дочерних элементов|
|TVN_KEYDOWN|Сообщает событие клавиатуры|
|TVN_SELCHANGED|Сообщает, выбор был перенесен с одного элемента в другой|
|TVN_SELCHANGING|Показывает, выделение перенесен с одного элемента в другой|
|TVN_SETDISPINFO|Уведомление для обновления сведений, поддерживаемых для элемента|

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

