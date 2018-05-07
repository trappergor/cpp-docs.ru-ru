---
title: Добавление элементов управления в лист свойств | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8437fcdaa04ce7dd2b0a214e4bd3a63ca421d014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adding-controls-to-a-property-sheet"></a>Добавление элементов управления на вкладку свойств
По умолчанию страницы свойств выделяет область окна для страницы свойств, индекс вкладки и кнопки OK, Отмена и применить. (Немодальный лист свойств не имеет OK, Отмена и применить кнопки.) Другие элементы управления можно добавить в таблицу свойств. Например можно добавить в окно предварительного просмотра справа от области страницы свойств, чтобы показать пользователю, как будет выглядеть текущие параметры, если применяется к внешнему объекту.  
  
 Добавлении элементов управления в диалоговое окно листа свойств в `OnCreate` обработчика. Учета дополнительных элементов управления обычно требуется увеличение размера диалоговое окно листа свойств. После вызова метода базового класса **CPropertySheet::OnCreate**, вызовите [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) для получения ширину и высоту окно страницы свойств, выделенных на данный момент, разверните прямоугольника измерений и вызова [Функции MoveWindow](../mfc/reference/cwnd-class.md#movewindow) для изменения размера окно страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)   
 [CPropertyPage-класс](../mfc/reference/cpropertypage-class.md)   
 [Класс CPropertySheet](../mfc/reference/cpropertysheet-class.md)
