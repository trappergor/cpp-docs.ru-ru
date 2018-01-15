---
title: "Задание сочетания клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cd52fca8415196fc1393cc49fe7830f6ca2cfd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setting-a-hot-key"></a>Задание сочетания клавиш
Приложение может использовать сведения, предоставляемые сочетания клавиш ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) элемента управления в одном из двух способов:  
  
-   Настройка Глобальные сочетания клавиш для активации окна nonchild, отправляя [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) сообщение в окно активироваться.  
  
-   Настройка сочетания клавиш определенного потока с помощью вызова функции Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

