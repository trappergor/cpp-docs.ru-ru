---
title: Работа с элементом управления панели инструментов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e488d4b475cbc73f57bb90ccd081b6d490221d58
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202264"
---
# <a name="working-with-the-toolbar-control"></a>Работа с элементом управления панели инструментов
В этой статье объясняется, как вы можете получить доступ к [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объектом базового [CToolBar](../mfc/reference/ctoolbar-class.md) для большего контроля над панелей инструментов. Это довольно сложная тема.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Для доступа к общего элемента управления панели инструментов базовый объект CToolBar  
  
1.  Вызовите [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
 `GetToolBarCtrl` Возвращает ссылку на [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта. Ссылку можно использовать для вызова функции-члены класса элемента управления панели инструментов.  
  
> [!CAUTION]
>  Во время вызова методов `CToolBarCtrl` **получить** функции защищена, будьте осторожны при вызове метода **задать** функции. Это довольно сложная тема. Обычно не требуется доступ к базовому элементу управления панели инструментов.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений  
  
-   [Элементы управления (стандартные элементы управления Windows)](../mfc/controls-mfc.md)  
  
-   [Основные сведения о панели инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Динамическое изменение размера панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)  
  
-   [Состояния flyby](../mfc/toolbar-tool-tips.md)  
  
-   [Обработка уведомлений всплывающих подсказок](../mfc/handling-tool-tip-notifications.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) классы  
  
-   [Обработка уведомлений о настройке](../mfc/handling-customization-notifications.md)  
  
-   [Несколько панелей инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)  
  
-   [Панели элементов управления](../mfc/control-bars.md)  
  
 Общие сведения об использовании стандартных элементов управления Windows, см. в разделе [стандартные элементы управления](/windows/desktop/Controls/common-controls-intro).  
  
## <a name="see-also"></a>См. также  
 [Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)

