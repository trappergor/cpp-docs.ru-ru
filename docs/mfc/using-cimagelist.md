---
title: "Использование CImageList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImageList
dev_langs: C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 053e670b5a6d932c50e2f967ee38cf9191710ff4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-cimagelist"></a>Использование CImageList
Список изображений, представленный классом [CImageList](../mfc/reference/cimagelist-class.md), — это совокупность аналогичного размера изображения, каждый из которых можно ссылаться по его индексу. Списки изображений используются для эффективного управления большими наборами значков и точечных рисунков. Списки изображений — сами по себе не элементы управления, так как они не являются windows; Тем не менее, они используются с несколько разных типов элементов управления, включая элементы управления списком ([CListCtrl](../mfc/reference/clistctrl-class.md)), элементы управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) и табуляции элементов управления ([CTabCtrl](../mfc/reference/ctabctrl-class.md)).  
  
 Все образы в список изображений, содержатся в один расширенный точечного рисунка в формате на экране устройства. Список изображений может также включать монохромный точечный рисунок, содержащий маски, используемый для рисования изображения прозрачно (стиль значка). `CImageList`предоставляет функции-члены, позволяющие Рисование изображений, создать и уничтожить списков изображений, добавление и удаление изображений из, замены изображений, объединение изображений и перетащите изображения.  
  
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

