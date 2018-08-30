---
title: Добавление вкладок в элемент управления вкладками | Документация Майкрософт
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
ms.openlocfilehash: cb8caad0b7d1f632a2d97e4ea6bda7c93a2b4d74
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218301"
---
# <a name="adding-tabs-to-a-tab-control"></a>Добавление вкладок в элемент управления "Вкладка"
После создания вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), добавьте столько вкладок, как требуется.  
  
### <a name="to-add-a-tab-item"></a>Чтобы добавить элемент вкладки  
  
1.  Подготовка [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуры.  
  
2.  Вызовите [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), передачи структуры.  
  
3.  Повторите шаги 1 и 2 для элементов дополнительные вкладки.  
  
 Дополнительные сведения см. в разделе [Создание элемента управления Tab](/windows/desktop/Controls/tab-controls) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

