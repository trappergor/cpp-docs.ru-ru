---
title: Добавление элементов в элемент управления "Заголовок"
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: 897612c6d5ac96704cc0a945df65146e6a01480a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264382"
---
# <a name="adding-items-to-the-header-control"></a>Добавление элементов в элемент управления "Заголовок"

После создания элемента управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) в его родительского окна, добавьте «заголовка произвольное число условий фильтра» необходимо: обычно по одному на столбец.

### <a name="to-add-a-header-item"></a>Чтобы добавить элемент заголовка

1. Подготовка [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуры.

1. Вызовите [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), передачи структуры.

1. Повторите шаги 1 и 2 для дополнительных элементов.

Дополнительные сведения см. в разделе [Добавление элемента управления заголовка](/windows/desktop/Controls/header-controls) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
