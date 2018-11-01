---
title: Создание списков изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 52f375c98b5f73e0f5721c951c94e4b24f0bc224
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608684"
---
# <a name="creating-the-image-lists"></a>Создание списков изображений

Создание списков изображений не отличается, независимо от используемого метода [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../mfc/reference/clistctrl-class.md).

> [!NOTE]
>  Вы должны образ только списки, если элемент управления списка включает `LVS_ICON` стиля.

Используйте класс `CImageList` создать один или несколько списков изображений (для полного размера значков Мелкие значки и состояний). См. в разделе [CImageList](../mfc/reference/cimagelist-class.md)и см. в разделе [списки изображений представление списка](/windows/desktop/Controls/using-list-view-controls) в пакете Windows SDK.

Вызовите [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) для каждого образ списка; передать указатель на соответствующий `CImageList` объекта.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

