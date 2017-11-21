---
title: "Добавление элементов управления в лист свойств | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5623f95a77710e0ffbfa8a444de6f569f24105e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>Добавление элементов управления на вкладку свойств
По умолчанию страницы свойств выделяет область окна для страницы свойств, индекс вкладки и кнопки OK, Отмена и применить. (Немодальный лист свойств не имеет OK, Отмена и применить кнопки.) Другие элементы управления можно добавить в таблицу свойств. Например можно добавить в окно предварительного просмотра справа от области страницы свойств, чтобы показать пользователю, как будет выглядеть текущие параметры, если применяется к внешнему объекту.  
  
 Добавлении элементов управления в диалоговое окно листа свойств в `OnCreate` обработчика. Учета дополнительных элементов управления обычно требуется увеличение размера диалоговое окно листа свойств. После вызова метода базового класса **CPropertySheet::OnCreate**, вызовите [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) для получения ширину и высоту окно страницы свойств, выделенных на данный момент, разверните прямоугольника измерений и вызова [Функции MoveWindow](../mfc/reference/cwnd-class.md#movewindow) для изменения размера окно страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)   
 [CPropertyPage-класс](../mfc/reference/cpropertypage-class.md)   
 [Класс CPropertySheet](../mfc/reference/cpropertysheet-class.md)
