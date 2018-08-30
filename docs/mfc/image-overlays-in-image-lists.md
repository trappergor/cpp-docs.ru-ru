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
ms.openlocfilehash: 4369fe312669f75eb8217be7a6a09c4287f7cc8b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210717"
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений
Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) включает в себя список образов для использования в качестве маски наложения. «Наложения маски» — это образ, прозрачным через другое изображение. Любое другое изображение может использоваться в качестве маски наложения. Можно указать до четырех наложения маски для списка изображений.  
  
 Добавить индекс изображения в список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс изображения и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не с нуля.  
  
 Отображение маски наложения поверх образа с помощью одного вызова `Draw`. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос, чтобы указать индекс маски наложения. Наложение изображения также можно указать при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функция-член.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

