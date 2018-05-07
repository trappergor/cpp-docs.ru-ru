---
title: Сортировка элементов в элемент управления заголовка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfa84326286b03f3ed0154138ed7f847440df284
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ordering-items-in-the-header-control"></a>Сортировка элементов в элементе управления "Заголовок"
После [добавить элементы управления заголовка](../mfc/adding-items-to-the-header-control.md), можно управлять и получать сведения о порядке их со следующими функциями:  
  
-   [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) и [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)  
  
     Получает и задает порядок элементов заголовка справа налево.  
  
-   [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).  
  
     Получает значение индекса для определенного заголовка элемента.  
  
 В дополнение к предыдущей функции-члены `HDS_DRAGDROP` стиль пользователь может перетаскивать элементы заголовка в элементе управления заголовка. Дополнительные сведения см. в разделе [Предоставление поддержки перетаскивания и вставки для элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

