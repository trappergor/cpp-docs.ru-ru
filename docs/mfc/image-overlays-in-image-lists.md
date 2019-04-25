---
title: Перекрытия изображений в списках изображений
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: 8dd0b30ef29a48ebc763564e6fe23632cd300831
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407969"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений

Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) включает в себя список образов для использования в качестве маски наложения. «Наложения маски» — это образ, прозрачным через другое изображение. Любое другое изображение может использоваться в качестве маски наложения. Можно указать до четырех наложения маски для списка изображений.

Добавить индекс изображения в список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс изображения и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не с нуля.

Отображение маски наложения поверх образа с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос, чтобы указать индекс маски наложения. Наложение изображения также можно указать при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функция-член.

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
