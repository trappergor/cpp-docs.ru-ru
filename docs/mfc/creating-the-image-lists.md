---
title: Создание списков изображений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5f5ac8396c32e56e4c0f2f951f45bb33714822
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-image-lists"></a>Создание списков изображений
Создание списков изображений одинаково независимо от используемого [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Вы должны образ только списки, если элемент управления списка включает `LVS_ICON` стиля.  
  
 Используйте класс `CImageList` для создания одного или нескольких списков изображений (для полного размера значков Мелкие значки и состояния). В разделе [CImageList](../mfc/reference/cimagelist-class.md)и в разделе [списки изображений представление списка](http://msdn.microsoft.com/library/windows/desktop/bb774736) в Windows SDK.  
  
 Вызовите [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) для каждого образ списка; передать указатель на соответствующий `CImageList` объекта.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

