---
title: Настройка элемента заголовка&#39;s внешний вид | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b58af1efc0558fe9195f56c31df11827d57f731
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-the-header-item39s-appearance"></a>Настройка элемента заголовка&#39;внешний вид s
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

