---
title: Инициализация частей объекта CStatusBarCtrl | Документы Microsoft
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
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89cea1516924530f821003affd96e2848687882b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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

