---
title: "Изображения перекрытия в списках изображений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e70365040b5f009e634a4867a4a1f974d47bd61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="image-overlays-in-image-lists"></a>Перекрытия изображений в списках изображений
Каждый список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) содержит список изображений, используемых как наложение маски. «Наложение маски» — это изображение, прозрачным через другое изображение. Любое изображение может использоваться в качестве маски наложения. Можно указать до четырех маски наложения каждого списка изображений.  
  
 Добавить индекс изображения список масок наложения с помощью [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) функция-член, индекс образа и индекс маски наложения. Обратите внимание, что индексы для наложения маски от единицы, а не от нуля.  
  
 Создайте маски наложения за образа с помощью одного вызова **нарисовать**. Параметры включают индекс изображения для рисования и индекс маски наложения. Необходимо использовать [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) макрос для указания индекса маски наложения. Можно также указать изображение перекрытия при вызове [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

