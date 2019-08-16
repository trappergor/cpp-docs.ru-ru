---
title: Создание списков изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 6687b62b70103894d957a21019008e8781385feb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508781"
---
# <a name="creating-the-image-lists"></a>Создание списков изображений

Создание списков изображений одинаково при использовании [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../mfc/reference/clistctrl-class.md).

> [!NOTE]
>  Если элемент управления "список" содержит стиль, `LVS_ICON` необходимы только списки изображений.

Класс `CImageList` используется для создания одного или нескольких списков изображений (для значков полного размера, мелких значков и состояний). См. раздел [CImageList](../mfc/reference/cimagelist-class.md)и [Просмотр списка изображений](/windows/win32/Controls/using-list-view-controls) в Windows SDK.

Вызовите [CListCtrl:: сетимажелист](../mfc/reference/clistctrl-class.md#setimagelist) для каждого списка изображений. передайте указатель на соответствующий `CImageList` объект.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
