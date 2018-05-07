---
title: Использование всплывающих подсказок в объекте CStatusBarCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323f2861da9fcc498e34792c30c763b4dffb2fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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

