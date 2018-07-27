---
title: Добавление вкладок в наборе вкладок | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86032bd3d1ce10221cb5d8094e4ba6de866e1eea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342857"
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

