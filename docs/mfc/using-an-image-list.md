---
title: "Использование списка изображений | Документы Microsoft"
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
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4321649bf4e8fe0e34fef8fe37b8c96598bef2c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-image-list"></a>Использование списка изображений
Типичное использование списка изображений соответствует шаблону ниже:  
  
-   Создать [CImageList](../mfc/reference/cimagelist-class.md) объекта и вызвать одну из перегрузок его [создать](../mfc/reference/cimagelist-class.md#create) функции для создания списка изображений и присоединить его к `CImageList` объекта.  
  
-   Если не добавить изображения при создании списка изображений, добавление изображений в список изображений, вызвав [добавить](../mfc/reference/cimagelist-class.md#add) или [чтения](../mfc/reference/cimagelist-class.md#read) функции-члена.  
  
-   Связать список изображений с элементом управления путем вызова функции-члена этого элемента управления или рисование изображений из списка изображений, вручную с помощью списка изображений [нарисовать](../mfc/reference/cimagelist-class.md#draw) функции-члена.  
  
-   Возможно позволяют пользователю перетащить изображения, с помощью встроенной поддержки списка изображений для перетаскивания.  
  
> [!NOTE]
>  Если был создан список изображений с **новый** оператором, требуется уничтожить `CImageList` объекта, когда вы завершили работу с ним.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

