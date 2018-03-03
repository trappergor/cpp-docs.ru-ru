---
title: "Использование всплывающих подсказок в объекте CStatusBarCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Использование всплывающих подсказок в объекте CStatusBarCtrl
Чтобы включить подсказки для строки состояния, создайте `CStatusBarCtrl` объекта с **SBT_TOOLTIPS** стиля.  
  
> [!NOTE]
>  Если вы используете `CStatusBar` объекта, чтобы реализовать строка состояния, используйте `CStatusBar::CreateEx` функции. Он позволяет указать дополнительные стили для embedded **CStatusBarCtrl** объекта.  
  
 Один раз `CStatusBarCtrl` объект был успешно создан, используйте [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) и [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) и извлечения текст подсказки для определенной области.  
  
 После задания всплывающая подсказка отображается только в том случае, если значение имеет значок, а не текста или весь текст не может быть отображен в части. Всплывающие подсказки в простом режиме не поддерживаются.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

