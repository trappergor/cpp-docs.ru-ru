---
title: "Инициализация частей объекта CStatusBarCtrl | Документы Microsoft"
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
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b713a46db13508df5ba80b21e3dfe938261eec65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Инициализация частей объекта CStatusBarCtrl
По умолчанию строка состояния отображает сведения о состоянии с помощью отдельных панелей. Эти области (также называемый частей) может содержать строку текста, значок или оба.  
  
 Используйте [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) для определения, сколько части и длину, строка состояния будет иметь. После создания части строки состояния, выполнять вызовы [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) и [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) для задания текста или значка для определенной части строки состояния. Когда элемент был успешно установлен, элемент управления перерисовывается автоматически.  
  
 Следующий пример инициализирует существующий `CStatusBarCtrl` объекта (`m_StatusBarCtrl`) с помощью четырех панелей и затем задает значок (IDI_ICON1) и текст во второй части.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 Дополнительные сведения о задании режима `CStatusBarCtrl` объект для простой, см. в разделе [Установка режима объекта CStatusBarCtrl](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

