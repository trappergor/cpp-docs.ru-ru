---
title: Использование CImageList | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CImageList
dev_langs:
- C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd30b21b1ec635c6d5b5f2f5c6c6d9eb6fc3fa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385795"
---
# <a name="using-cimagelist"></a>Использование CImageList
Список изображений, представленный классом [CImageList](../mfc/reference/cimagelist-class.md), — это совокупность аналогичного размера изображения, каждый из которых можно ссылаться по его индексу. Списки изображений используются для эффективного управления большими наборами значков и точечных рисунков. Списки изображений — сами по себе не элементы управления, так как они не являются windows; Тем не менее, они используются с несколько разных типов элементов управления, включая элементы управления списком ([CListCtrl](../mfc/reference/clistctrl-class.md)), элементы управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) и табуляции элементов управления ([CTabCtrl](../mfc/reference/ctabctrl-class.md)).  
  
 Все образы в список изображений, содержатся в один расширенный точечного рисунка в формате на экране устройства. Список изображений может также включать монохромный точечный рисунок, содержащий маски, используемый для рисования изображения прозрачно (стиль значка). `CImageList` предоставляет функции-члены, позволяющие Рисование изображений, создать и уничтожить списков изображений, добавление и удаление изображений из, замены изображений, объединение изображений и перетащите изображения.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Типы списков изображений](../mfc/types-of-image-lists.md)  
  
-   [Использование списка изображений](../mfc/using-an-image-list.md)  
  
-   [Управление списками изображений](../mfc/manipulating-image-lists.md)  
  
-   [Рисование изображений из списка изображений](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Перекрытия изображений в списках изображений](../mfc/image-overlays-in-image-lists.md)  
  
-   [Перетаскивание изображений из списка изображений](../mfc/dragging-images-from-an-image-list.md)  
  
-   [Сведения об изображениях в списках изображений](../mfc/image-information-in-image-lists.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../mfc/controls-mfc.md)

