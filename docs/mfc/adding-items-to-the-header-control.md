---
title: Добавление элементов управления заголовка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69d64265a94df2770e3a234ab992130b4809f9e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adding-items-to-the-header-control"></a>Добавление элементов в элемент управления "Заголовок"
После создания элемента управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) в его родительском окне добавить столько «заголовок элементов» необходимо: как правило, каждого столбца.  
  
### <a name="to-add-a-header-item"></a>Чтобы добавить элемент заголовка  
  
1.  Подготовка [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуры.  
  
2.  Вызовите [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), передачи структуры.  
  
3.  Повторите шаги 1 и 2 для дополнительных элементов.  
  
 Дополнительные сведения см. в разделе [Добавление элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775238) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

