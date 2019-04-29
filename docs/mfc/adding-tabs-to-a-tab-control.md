---
title: Добавление вкладок в элемент управления "Вкладка"
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: f769de7bcf3e410cca717c17237d1e49ef8562c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394771"
---
# <a name="adding-tabs-to-a-tab-control"></a>Добавление вкладок в элемент управления "Вкладка"

После создания вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), добавьте столько вкладок, как требуется.

### <a name="to-add-a-tab-item"></a>Чтобы добавить элемент вкладки

1. Подготовка [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуры.

1. Вызовите [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), передачи структуры.

1. Повторите шаги 1 и 2 для элементов дополнительные вкладки.

Дополнительные сведения см. в разделе [Создание элемента управления Tab](/windows/desktop/Controls/tab-controls) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
