---
title: Добавление элементов в элемент управления "Заголовок"
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: d9a35123ddbe77b8e5e1779651fc4cde233863ae
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509316"
---
# <a name="adding-items-to-the-header-control"></a>Добавление элементов в элемент управления "Заголовок"

После создания элемента управления "заголовок" ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) в его родительском окне Добавьте столько элементов заголовка, сколько требуется: обычно по одному на столбец.

### <a name="to-add-a-header-item"></a>Добавление элемента заголовка

1. Подготовьте структуру [HD_ITEM](/windows/win32/api/commctrl/ns-commctrl-_hd_itemw) .

1. Вызовите метод [CHeaderCtrl:: InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), передав структуру.

1. Повторите шаги 1 и 2 для дополнительных элементов.

Дополнительные сведения см. в разделе [Добавление элемента в элемент управления "заголовок](/windows/win32/Controls/header-controls) " в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
