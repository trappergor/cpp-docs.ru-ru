---
title: "Глобальные сочетания клавиш | Документы Microsoft"
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
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 48f3e2a1e0c1461180291342a8cd18682173e8bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="global-hot-keys"></a>Глобальные сочетания клавиш
Глобальные сочетания клавиш связан с определенной nonchild окна. Он позволяет пользователям активировать окна из любой части системы. Приложение задает глобальные сочетания клавиш для определенного окна, отправляя [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) сообщение для этого окна. Для экземпляра Если `m_HotKeyCtrl` — [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) объекта и `pMainWnd` является указателем в окно, активируемый при нажатии сочетания клавиш, следующий код может использовать для сопоставления сочетания клавиш, заданные в элементе управления с окна, на который указывает `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 Каждый раз, когда пользователь нажимает Глобальные сочетания клавиш, окна, указанную получает [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) сообщение, указывающее **SC_HOTKEY** как тип команды. Это сообщение также активирует окно, получает его. Поскольку это сообщение не содержит все сведения о точный ключ, которая была нажата, с помощью этого метода не может различать разные сочетания клавиш, которые могут быть присоединены к окно. Сочетания клавиш остается действительным, пока приложение, отправляющее **WM_SETHOTKEY** завершает работу.  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

