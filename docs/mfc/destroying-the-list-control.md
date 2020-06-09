---
title: Уничтожение элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: d128a613a2a4cb595f362f843a5ae2eba830e538
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621898"
---
# <a name="destroying-the-list-control"></a>Уничтожение элемента управления "Список"

Если вы внедряете объект [CListCtrl](reference/clistctrl-class.md) в качестве элемента данных класса представления или диалогового окна, он уничтожается при уничтожении его владельца. При использовании [CListView](reference/clistview-class.md)платформа удаляет элемент управления, когда он уничтожает представление.

Если некоторые данные списка будут храниться в приложении, а не в элементе управления "список", необходимо будет отменять его освобождение. Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](/windows/win32/Controls/using-list-view-controls) в Windows SDK.

Кроме того, вы несете ответственность за отмену выделения всех созданных вами списков изображений, связанных с объектом элемента управления List.

## <a name="see-also"></a>См. также раздел

[Использование CListCtrl](using-clistctrl.md)<br/>
[Элементы управления](controls-mfc.md)
