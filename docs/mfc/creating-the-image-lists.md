---
title: "Создание списков изображений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfb42dc2c14b5092aeb667ea22008abe4d581a6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

