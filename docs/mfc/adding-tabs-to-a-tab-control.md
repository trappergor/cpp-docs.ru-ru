---
title: Добавление вкладок в элемент управления "Вкладка"
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: 8915b3af083ebe318e8527b2f83099bf61e7e3ce
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509308"
---
# <a name="adding-tabs-to-a-tab-control"></a>Добавление вкладок в элемент управления "Вкладка"

После создания элемента управления "Вкладка" ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) добавьте столько вкладок, сколько необходимо.

### <a name="to-add-a-tab-item"></a>Добавление элемента вкладки

1. Подготовьте структуру [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) .

1. Вызовите метод [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), передав структуру.

1. Повторите шаги 1 и 2 для дополнительных элементов вкладки.

Дополнительные сведения см. в разделе [Создание элемента управления "Вкладка"](/windows/win32/Controls/tab-controls) в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
