---
title: Перекрытия изображений в списках изображений
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: dc5c28a38d3024f3d8cbd1fa8b9fe9c1c8a09f93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603103"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений

Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) включает в себя список образов для использования в качестве маски наложения. «Наложения маски» — это образ, прозрачным через другое изображение. Любое другое изображение может использоваться в качестве маски наложения. Можно указать до четырех наложения маски для списка изображений.

Добавить индекс изображения в список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс изображения и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не с нуля.

Отображение маски наложения поверх образа с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос, чтобы указать индекс маски наложения. Наложение изображения также можно указать при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функция-член.

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

