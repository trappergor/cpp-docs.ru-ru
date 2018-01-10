---
title: "Использование CHotKeyCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CHotKeyCtrl
dev_langs: C++
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36d577369dea4f5fe2fffa9801bbd8ae8501f71a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-chotkeyctrl"></a>Использование CHotKeyCtrl
Горячий ключа элемента управления, представленный классом [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), — окно, которое отображает текстовое представление сочетание клавиш, которые пользователь вводит в него, например CTRL + SHIFT + Q. Это также обеспечивает внутреннее представление этого ключа в виде виртуального кода клавиши и набор флагов, которые представляют состояние сдвига. Горячий ключа управления фактически не задано сочетание клавиш — это зависит от программы. (Список стандартных кодов виртуального ключа, см. в Winuser.h.)  
  
 Используйте горячей ключа элемента управления для получения входных данных пользователя для какие сочетания клавиш, связываемый с окном или поток. Элементы управления сочетанием клавиш часто используются в диалоговых окнах, такие как может отображаться при запросе пользователя, чтобы назначить сочетание клавиш. Возлагается программы для получения значения, описывающие сочетания клавиш из горячей ключа элемента управления и вызывать соответствующие функции для присоединения к ним сочетания клавиш окна или поток.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Использование элемента управления "Сочетание клавиш"](../mfc/using-a-hot-key-control.md)  
  
-   [Задание сочетания клавиш](../mfc/setting-a-hot-key.md)  
  
-   [Глобальные сочетания клавиш](../mfc/global-hot-keys.md)  
  
-   [Сочетания клавиш для определенного потока](../mfc/thread-specific-hot-keys.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../mfc/controls-mfc.md)

