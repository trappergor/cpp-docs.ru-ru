---
title: Изображения перекрытия в списках изображений | Документы Microsoft
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
ms.openlocfilehash: 93d37b49a949ab29e0ae888d9c961da086ee4ca4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928600"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений
Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) содержит список изображений, используемых как наложение маски. «Наложение маски» — это изображение, прозрачным через другое изображение. Любое изображение может использоваться в качестве маски наложения. Можно указать до четырех маски наложения каждого списка изображений.  
  
 Добавить индекс изображения список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс образа и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не от нуля.  
  
 Создайте маски наложения за образа с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) макрос для указания индекса маски наложения. Можно также указать изображение перекрытия при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

