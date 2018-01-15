---
title: "Работа с элементом управления панели инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 475b44b856c874064a4ccbdaf7b648342eb9c657
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-the-toolbar-control"></a>Работа с элементом управления панели инструментов
В этой статье объясняется, как можно доступ к [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) основным [CToolBar](../mfc/reference/ctoolbar-class.md) для большего контроля над панелей инструментов. Это довольно сложная тема.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Для доступа к стандартного элемента управления панель инструментов базовый объект CToolBar  
  
1.  Вызовите [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
 `GetToolBarCtrl`Возвращает ссылку на [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта. Ссылку можно использовать для вызова функции-члены класса элемента управления панели инструментов.  
  
> [!CAUTION]
>  При вызове `CToolBarCtrl` **получить** функции безопасна, соблюдайте осторожность при вызове **задать** функции. Это довольно сложная тема. Обычно вам не потребуется доступ к базовому элементу управления панели инструментов.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Элементы управления (Общие элементы управления Windows)](../mfc/controls-mfc.md)  
  
-   [Принципы работы инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Динамическое изменение размера панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)  
  
-   [Обновление строки состояния flyby](../mfc/toolbar-tool-tips.md)  
  
-   [Обработка уведомлений всплывающих подсказок](../mfc/handling-tool-tip-notifications.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) классы  
  
-   [Обработка уведомлений о настройке](../mfc/handling-customization-notifications.md)  
  
-   [Несколько панелей инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)  
  
-   [Панели элементов управления](../mfc/control-bars.md)  
  
 Общие сведения об использовании общих элементов управления Windows см. в разделе [стандартные элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## <a name="see-also"></a>См. также  
 [Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)

