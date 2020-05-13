---
title: Создание списков изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 440ab6fdfe7663557f6c6a6607e617c793d26674
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371572"
---
# <a name="creating-the-image-lists"></a>Создание списков изображений

Создание списков изображений является тем же, используете ли вы [CListView](../mfc/reference/clistview-class.md) или [CListCtrl.](../mfc/reference/clistctrl-class.md)

> [!NOTE]
> Вам нужны списки изображений только `LVS_ICON` в том случае, если элемент управления списком включает в себя стиль.

Используйте `CImageList` класс для создания одного или нескольких списков изображений (для полноразмерных иконок, небольших иконок и состояний). См [CImageList](../mfc/reference/cimagelist-class.md)и [список просмотров](/windows/win32/Controls/using-list-view-controls) списков в SDK Windows.

Звоните [cListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) для каждого списка изображений; передать указатель на `CImageList` соответствующий объект.

## <a name="see-also"></a>См. также раздел

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
