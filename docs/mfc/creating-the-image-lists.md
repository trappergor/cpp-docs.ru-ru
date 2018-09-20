---
title: Создание списков изображений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7772b6b6a809e5a89e2cb6b0ef3edb68821805c2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372319"
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

