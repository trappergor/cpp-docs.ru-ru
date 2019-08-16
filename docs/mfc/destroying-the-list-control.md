---
title: Уничтожение элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 5004026da6bb309cc2c966384724b7b98e254e1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508698"
---
# <a name="destroying-the-list-control"></a>Уничтожение элемента управления "Список"

Если вы внедряете объект [CListCtrl](../mfc/reference/clistctrl-class.md) в качестве элемента данных класса представления или диалогового окна, он уничтожается при уничтожении его владельца. При использовании [CListView](../mfc/reference/clistview-class.md)платформа удаляет элемент управления, когда он уничтожает представление.

Если некоторые данные списка будут храниться в приложении, а не в элементе управления "список", необходимо будет отменять его освобождение. Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](/windows/win32/Controls/using-list-view-controls) в Windows SDK.

Кроме того, вы несете ответственность за отмену выделения всех созданных вами списков изображений, связанных с объектом элемента управления List.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
