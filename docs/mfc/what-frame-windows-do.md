---
title: Окон фрейма | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ed903238a812188d73093211265c9c8c028b0ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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

