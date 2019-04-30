---
title: Уничтожение элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 963da9e6db2f0fe063dee1ca19ab23f545ed5e76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392893"
---
# <a name="destroying-the-list-control"></a>Уничтожение элемента управления "Список"

При внедрении вашей [CListCtrl](../mfc/reference/clistctrl-class.md) объект как член данных класса представления или диалогового окна, он уничтожается при уничтожении его владельцем. Если вы используете [CListView](../mfc/reference/clistview-class.md), платформа уничтожает элемент управления, когда она окончательно удаляет представление.

Если упорядочить для некоторых данных списка для сохранения в приложение, а не в элементе управления списком, необходимо упорядочить для его освобождения. Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](/windows/desktop/Controls/using-list-view-controls) в пакете Windows SDK.

Кроме того вы несете ответственность за освобождение любые списки изображений, вы создали и связанный с объектом элемента управления списка.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
