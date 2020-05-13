---
title: Предоставление поддержки перетаскивания для элементов заголовка
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 8dfaabf3da62c216d3da662f59c57b63e695d9ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371165"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Предоставление поддержки перетаскивания для элементов заголовка

Чтобы обеспечить поддержку перетаскивания элементов заголовка, укажите HDS_DRAGDROP стиль. Поддержка задрапчивания элементов заголовка дает пользователю возможность переупорядочить элементы заголовка элементы управления заголовком. Поведение по умолчанию обеспечивает полупрозрачное изображение перетаскивания перетаскивания элемента заголовка и визуальный индикатор нового положения, если элемент заголовка удален.

Как и в случае с обычной функциональностью перетаскивания, можно расширить поведение перетаскивания по умолчанию, обправив HDN_BEGINDRAG и HDN_ENDDRAG уведомлений. Вы также можете настроить внешний вид изображения перетаскивания, переопределив функцию члена [CHeaderCtrl::CreateDragImage.](../mfc/reference/cheaderctrl-class.md#createdragimage)

> [!NOTE]
> Если вы предоставляете поддержку перетаскивания для элемента управления заголовком в элементе управления списком, см. раздел Расширенный стиль в теме [«Стиль управления изменяющимся списками».](../mfc/changing-list-control-styles.md)

## <a name="see-also"></a>См. также раздел

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)
