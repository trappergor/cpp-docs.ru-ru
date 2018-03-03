---
title: "Использование списков изображений с элементами управления заголовок | Документы Microsoft"
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
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7a51aadc10a7722875597813e24ceb5960ab459
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-with-header-controls"></a>Использование списков изображений с элементами управления "Заголовок"
Элементы заголовка, имеют возможность отображать изображения в элементе заголовка. Этот образ, сохраняются в списке связанное изображение 16 x 16 пикселей и имеет те же характеристики, как изображения значков, используемых в элементе управления списком. Чтобы успешно реализовать это поведение, необходимо сначала создать и инициализировать список изображений, связать список с элементом управления заголовка и затем изменить атрибуты элемента заголовка, который будет отображать изображения.  
  
 В следующей процедуре показано сведения, используя указатель на элемент управления заголовком (`m_pHdrCtrl`) и указатель на список изображений (`m_pHdrImages`).  
  
### <a name="to-display-an-image-in-a-header-item"></a>Для отображения изображения в элементе заголовка  
  
1.  Создать новый список изображений (или использование существующего объекта списка изображений) с помощью [CImageList](../mfc/reference/cimagelist-class.md) конструктор, хранение результирующий указатель.  
  
2.  Инициализируйте новый объект списка изображений, вызвав [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Следующий код является примером этого вызова.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]  
  
3.  Добавление изображений для каждого элемента заголовка. Следующий код добавляет два стандартных образов.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]  
  
4.  Связать список изображений с элементом управления заголовка с помощью вызова [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).  
  
5.  Изменение элемента заголовка для отображения изображения в списке нужный образ. В следующем примере назначается первое изображение из `m_phdrImages`, к первому элементу заголовка `m_pHdrCtrl`.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]  
  
 Подробные сведения о используются значения параметров, обратитесь к соответствующей [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).  
  
> [!NOTE]
>  Можно иметь несколько элементов управления, используя тот же набор изображений. Например в элементе представления стандартный список может быть списка изображений (из изображений с размером 16 x 16 пикселей) используется мелкий значок представление элемента управления представления списка и элементов заголовка элемента управления представления списка.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

