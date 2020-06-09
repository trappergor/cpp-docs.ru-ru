---
title: Создание списков изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: bbba01a6a8e08ea53e164656733aa06e03dd87a7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625951"
---
# <a name="creating-the-image-lists"></a>Создание списков изображений

Создание списков изображений одинаково при использовании [CListView](reference/clistview-class.md) или [CListCtrl](reference/clistctrl-class.md).

> [!NOTE]
> Если элемент управления "список" содержит стиль, необходимы только списки изображений `LVS_ICON` .

Класс используется `CImageList` для создания одного или нескольких списков изображений (для значков полного размера, мелких значков и состояний). См. раздел [CImageList](reference/cimagelist-class.md)и [Просмотр списка изображений](/windows/win32/Controls/using-list-view-controls) в Windows SDK.

Вызовите [CListCtrl:: сетимажелист](reference/clistctrl-class.md#setimagelist) для каждого списка изображений. передайте указатель на соответствующий `CImageList` объект.

## <a name="see-also"></a>См. также раздел

[Использование CListCtrl](using-clistctrl.md)<br/>
[Элементы управления](controls-mfc.md)
