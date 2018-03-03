---
title: "Управление элементом управления хода выполнения | Документы Microsoft"
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
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c75866cdcf947745db741a6626f01215e58932e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-the-progress-control"></a>Управление элементом управления "Индикатор выполнения"
Существует три способа, чтобы изменить текущую позицию элемента управления хода выполнения ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).  
  
-   Можно изменить положение величину предустановленную инкремента.  
  
-   Можно изменить положение по произвольного размера.  
  
-   Можно изменить положение конкретное значение.  
  
### <a name="to-change-the-position-by-a-preset-amount"></a>Изменение положения предустановленную величину  
  
1.  Используйте [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) функции-члена задайте значение приращения. По умолчанию это значение равно 10. Это значение обычно устанавливается как один первоначальных параметров для элемента управления. Значение шага может быть отрицательным.  
  
2.  Используйте [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) функции-члена увеличение позиции. Это вызывает перерисовку элементом управления.  
  
    > [!NOTE]
    >  `StepIt`вызовет перенос. Например, имея диапазон 1 -100, шаг 20 и положение 90, `StepIt` переместит позицию до 10.  
  
### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Чтобы изменить расположение, произвольного размера  
  
1.  Используйте [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) функции-члена для изменения положения. `OffsetPos`будет принимать отрицательные значения.  
  
    > [!NOTE]
    >  `OffsetPos`, в отличие от `StepIt`, не будет переносить позицию. Новое положение корректируется оставаться в пределах диапазона.  
  
### <a name="to-change-the-position-to-a-specific-value"></a>Изменение положения конкретное значение  
  
1.  Используйте [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) функции-члена для установить позицию конкретное значение. При необходимости новая позиция будет настроена и находиться в диапазоне.  
  
 Как правило элемент управления ходом выполнения используется исключительно для вывода. Чтобы получить текущее положение без указания нового значения, используйте [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).  
  
## <a name="see-also"></a>См. также  
 [Использование CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

