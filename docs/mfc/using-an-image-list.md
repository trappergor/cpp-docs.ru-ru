---
title: Использование списка изображений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5722a2ef8c4e93e4996ee243b3c01b6dd6aeca78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381609"
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

