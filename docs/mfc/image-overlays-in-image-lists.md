---
title: Изображение перекрытия в списках изображений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4052e06fe8aae1d149c3c09e88715d8270b361
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426566"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений

Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) включает в себя список образов для использования в качестве маски наложения. «Наложения маски» — это образ, прозрачным через другое изображение. Любое другое изображение может использоваться в качестве маски наложения. Можно указать до четырех наложения маски для списка изображений.

Добавить индекс изображения в список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс изображения и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не с нуля.

Отображение маски наложения поверх образа с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос, чтобы указать индекс маски наложения. Наложение изображения также можно указать при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функция-член.

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

