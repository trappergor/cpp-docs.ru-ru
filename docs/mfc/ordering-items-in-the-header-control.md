---
title: Сортировка элементов в элементе управления "Заголовок"
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: 5c4fef821efa697d41bf02ef1891efcf0fa21d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583514"
---
# <a name="ordering-items-in-the-header-control"></a>Сортировка элементов в элементе управления "Заголовок"

Когда вы закончите [добавлении элементов в элемент управления заголовка](../mfc/adding-items-to-the-header-control.md), можно управлять и получать сведения о их порядок со следующими функциями:

- [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) и [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

   Получает и задает порядок элементов заголовка слева направо.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

   Получает значение индекса для определенного заголовка элемента.

В дополнение к предыдущей функции-члены hds_dragdrop-стиль позволяет пользователю перетаскивать элементы заголовка в элементе управления заголовка. Дополнительные сведения см. в разделе [Предоставление поддержки перетаскивания и вставки для элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

