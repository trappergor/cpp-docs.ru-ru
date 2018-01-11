---
title: "Окон фрейма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5143bab1ea84392efe1bd5783889c45375365ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="what-frame-windows-do"></a>Функция окон фрейма
Помимо просто кадрирования представления, фреймов несут ответственность за многочисленные задачи, связанные с согласование кадра его в представлении и вместе с приложением. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) наследовать от [CFrameWnd](../mfc/reference/cframewnd-class.md), поэтому они имеют `CFrameWnd` возможности, а также новые возможности, добавленные ими. Дочерние окна примеры представления, элементы управления, такие как кнопки, списки и панели элементов управления, включая панели инструментов, строк состояния и индикаторы диалоговое окно.  
  
 Окна фрейма отвечает за управление структурой его дочерних окон. В платформе MFC окно фрейма помещает любой панели элементов управления, представления и другие дочерние окна внутри клиентской области.  
  
 Окна фрейма также перенаправляет команды, чтобы его представлений и может реагировать на сообщения уведомления из элемента управления windows.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Панели элементов управления (как они помещаются в фрейме окна)](../mfc/control-bars.md)  
  
-   [Управление меню, панелей элементов управления и сочетания клавиш (как они помещаются в фрейме окна)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Маршрутизация команд (из окна фрейма для ее просмотра и другие целевые объекты команд)](../mfc/command-routing.md)  
  
-   [Архитектура документа/View](../mfc/document-view-architecture.md)  
  
-   [Панели элементов управления](../mfc/control-bars.md)  
  
-   [Элементы управления](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Окна фрейма](../mfc/frame-windows.md)

