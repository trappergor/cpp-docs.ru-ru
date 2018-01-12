---
title: "Настройка элемента заголовка &#39; s внешний вид | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dacb5cc7aa1c6d7c74a07ee911c5887efe1d877b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-the-header-item39s-appearance"></a>Настройка элемента заголовка &#39; s внешний вид
Установив *dwStyle* параметр при создании элемента управления заголовка ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), можно определить внешний вид и поведение заголовка элементов или заголовка самого элемента управления.  
  
 Вот выборки стили, которые можно задать, и их назначение.  
  
-   Чтобы сделать элемент заголовка выглядеть как кнопки, используйте `HDS_BUTTONS` стиля.  
  
     Используйте этот стиль, если вы хотите выполнять действия в ответ на щелчок элемента заголовка, например сортировка данных по отдельному столбцу, как в Microsoft Outlook.  
  
-   Чтобы предоставить элементы заголовка в виде «отслеживание» при наведении на них указателя мыши, используйте `HDS_HOTTRACK` стиля.  
  
     Отслеживание отображает 3D структуры, когда указатель находится над объектом, в противном случае плоский в строке.  
  
-   Чтобы показать, следует ли скрыть заголовок элемента управления, используйте `HDS_HIDDEN` стиля.  
  
     `HDS_HIDDEN` Стиль указывает, что элемент управления заголовка предназначен для использования в качестве контейнера данных и не визуального элемента. Этот стиль не скрывает элемент управления автоматически, но вместо этого влияет на поведение `CHeaderCtrl::Layout`. Значение, возвращаемое в **cy** членом `WINDOWPOS` структуры будет равно нулю, указывающее, что элемент управления не должны быть видимыми для пользователя.  
  
 Дополнительные сведения об этих свойствах см. в разделе [элементы](http://msdn.microsoft.com/library/windows/desktop/bb775238) в Windows SDK. Сведения о добавлении элементов к элементу управления заголовка. в разделе [Добавление элементов управления заголовка](../mfc/adding-items-to-the-header-control.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

