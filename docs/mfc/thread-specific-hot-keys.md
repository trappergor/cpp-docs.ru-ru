---
title: "Сочетания клавиш для определенного потока | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 89c6ae27dacf5b8637c914c92b6805b1cc405353
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="thread-specific-hot-keys"></a>Сочетания клавиш для определенного потока
Приложение задает сочетание клавиш потоках ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) с помощью Windows **RegisterHotKey** функции. Когда пользователь нажимает сочетание клавиш потоках, Windows отправляет [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) сообщение из начала очереди сообщений для определенного потока. **WM_HOTKEY** сообщение содержит виртуального кода клавиши, состояние сдвига и определяемых пользователем идентификатор определенного сочетания клавиш, которая была нажата. Список стандартных кодов виртуального ключа см. в разделе Winuser.h. Дополнительные сведения в этом методе см. в разделе [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Обратите внимание, что флаги состояния сдвига при вызове **RegisterHotKey** не совпадают, возвращаемыми [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) функция-член; вам придется преобразовать эти флаги перед вызовом **RegisterHotKey**.  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

