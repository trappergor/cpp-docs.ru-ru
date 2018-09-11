---
title: Задание сочетания клавиш | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254d7532b83a4f30c0029b2488bb0b2111cce31d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219401"
---
# <a name="setting-a-hot-key"></a>Задание сочетания клавиш
Приложение может использовать сведения, предоставляемые сочетания клавиш ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) элемента управления в одном из двух способов:  
  
-   Настройте глобальные сочетания клавиш для активации окна nonchild, отправляя [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) сообщение в окно активации.  
  
-   Настройка сочетания клавиш конкретного потока путем вызова функции Windows [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

