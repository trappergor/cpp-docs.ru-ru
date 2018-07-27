---
title: Задание сочетания клавиш | Документы Microsoft
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
ms.openlocfilehash: 3987ddee98ae35e02a181e38cd71f181801aeb61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379649"
---
# <a name="setting-a-hot-key"></a>Задание сочетания клавиш
Приложение может использовать сведения, предоставляемые сочетания клавиш ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) элемента управления в одном из двух способов:  
  
-   Настройка Глобальные сочетания клавиш для активации окна nonchild, отправляя [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) сообщение в окно активироваться.  
  
-   Настройка сочетания клавиш определенного потока с помощью вызова функции Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

