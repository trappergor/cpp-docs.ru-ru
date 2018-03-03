---
title: "Классы панели элементов управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44fcecbf1d7ddb6c46469f25349d972c8b317809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="control-bar-classes"></a>Классы панели элементов управления
Панели элементов управления, присоединяются к фрейм окна. Они содержат кнопки, панели состояния или шаблона диалогового окна. Свободные панелей, также называемый палитры инструментов реализуются посредством присоединения их [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) объекта.  
  
## <a name="framework-control-bars"></a>Framework панелей элементов управления  
 Эти панели элементов управления являются неотъемлемой частью платформы MFC. Это проще и эффективнее, чем панелей, элементов управления Windows, так как они интегрированы с помощью платформы. Большинство приложений MFC использует эти панели элементов управления, а не панелей элементов управления Windows.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 Базовый класс для элементов управления MFC, перечисленные в этом разделе. Панель элементов управления — это окно, по краю фрейма окна. На панели управления может содержать `HWND`-основе дочерние элементы или элементы управления, не зависит от `HWND`, такие как кнопки панели инструментов.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Панель элементов управления, который основан на шаблон диалогового окна.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Поддерживает панель инструментов, которая может содержать дополнительные дочерние окна в форму элементов управления.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Панель инструментов управления windows, не содержащие команды кнопок с точечными рисунками на основе `HWND`. Этот класс используется большинство приложений MFC вместо `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 Базовый класс для строки состояния элемента управления windows. Этот класс используется большинство приложений MFC вместо `CStatusBarCtrl`.  
  
## <a name="windows-control-bars"></a>Панели элементов управления Windows  
 Эти панели элементов управления являются тонкой оболочками для соответствующих элементов управления Windows. Так как они не интегрирована с платформой, они являются труднее по сравнению с ранее в списке панелей элементов управления. Большинство приложений MFC использует ранее в списке панелей элементов управления.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Реализует управление внутренней `CRebar` объекта.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Окно горизонтальной обычно разделены на области, в которых выводятся сведения о состоянии приложения.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Предоставляет функциональные возможности стандартного элемента управления "панель инструментов" Windows.  
  
## <a name="related-classes"></a>Связанные классы  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Небольшое всплывающее окно, которое отображается одна строка текста, описывающая назначение инструмента в приложении.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Обрабатывает постоянное хранилище для закрепления данные о состоянии для панели элементов управления.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

