---
title: Перекрытия изображений в списках изображений
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: ec795193a28a68d8aee61e9932481a89c4b3e8e0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508389"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений

Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) содержит список изображений для использования в качестве масок наложения. "Маска оверлея" — это изображение, которое прозрачно рисуется на другом изображении. Любой образ можно использовать в качестве маски оверлея. Можно указать до четырех масок оверлея для каждого списка изображений.

Вы добавляете индекс изображения в список масок наложения с помощью функции члена [сетоверлайимаже](../mfc/reference/cimagelist-class.md#setoverlayimage) , индекса изображения и индекса маски оверлея. Обратите внимание, что индексы для масок наложения основаны на единицах, а не на нуле.

Вы рисуете маску наложения на изображение с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски оверлея. Для указания индекса маски наложения необходимо использовать макрос [индекстуверлаймаск](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) . Можно также указать изображение оверлея при вызове функции члена [дравиндирект](../mfc/reference/cimagelist-class.md#drawindirect) .

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
