---
title: Сочетания клавиш для определенного потока | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdd6cf2f2bb76c30f4cc00d75eb55d7d2c01fa7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="thread-specific-hot-keys"></a>Сочетания клавиш для определенного потока
Приложение задает сочетание клавиш потоках ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) с помощью Windows **RegisterHotKey** функции. Когда пользователь нажимает сочетание клавиш потоках, Windows отправляет [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) сообщение из начала очереди сообщений для определенного потока. **WM_HOTKEY** сообщение содержит виртуального кода клавиши, состояние сдвига и определяемых пользователем идентификатор определенного сочетания клавиш, которая была нажата. Список стандартных кодов виртуального ключа см. в разделе Winuser.h. Дополнительные сведения в этом методе см. в разделе [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Обратите внимание, что флаги состояния сдвига при вызове **RegisterHotKey** не совпадают, возвращаемыми [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) функция-член; вам придется преобразовать эти флаги перед вызовом **RegisterHotKey**.  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

