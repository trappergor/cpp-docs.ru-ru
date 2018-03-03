---
title: "Добавление вкладок в наборе вкладок | Документы Microsoft"
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
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46012a265c1ecefa7af63f829be22e6132e036cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-tabs-to-a-tab-control"></a>Добавление вкладок в элемент управления "Вкладка"
После создания управления "Вкладка" ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), добавьте любое количество вкладок, как необходимо.  
  
### <a name="to-add-a-tab-item"></a>Чтобы добавить элемент вкладки  
  
1.  Подготовка [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры.  
  
2.  Вызовите [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), передачи структуры.  
  
3.  Повторите шаги 1 и 2 для элементов дополнительные вкладки.  
  
 Дополнительные сведения см. в разделе [Создание элемента управления Tab](http://msdn.microsoft.com/library/windows/desktop/bb760550) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

