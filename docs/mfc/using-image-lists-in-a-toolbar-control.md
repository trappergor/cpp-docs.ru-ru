---
title: Использование списков изображений в элементе управления панели инструментов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76325d2b078f51860cad7fa3fab61ed7c518a41c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382854"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Использование списков изображений в элементе управления панели инструментов
По умолчанию изображения, используемые кнопки в элементе управления панели инструментов хранятся в виде единого растрового изображения. Однако можно также хранить изображения кнопки в наборе списков изображений. Объект элемента управления панели инструментов можно использовать до трех списков отдельных изображений:  
  
-   Включить список изображение, содержит изображения для кнопок панели инструментов, которая в настоящее время включены.  
  
-   Отключить список изображение, содержит изображения для кнопок панели инструментов, которая в данный момент отключены.  
  
-   Выделено изображения список содержит изображения для кнопки панели инструментов, выделяются в настоящее время. Этот список изображений используется только в том случае, если панель инструментов использует **TBSTYLE_FLAT** стиля.  
  
 При связывании с элементом управления панели инструментов используются эти списки изображений `CToolBarCtrl` объекта. Эта связь осуществляется с помощью обращений [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), и [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).  
  
 По умолчанию используется библиотекой MFC `CToolBar` класса для реализации панели инструментов приложения MFC. Тем не менее `GetToolBarCtrl` функции-члена можно использовать для получения встроенный `CToolBarCtrl` объекта. Затем может выполнять вызовы `CToolBarCtrl` использованием возвращенного объекта функции-члены.  
  
 В следующем примере демонстрируется этот способ, назначив активный (`m_ToolBarImages`) и отключен (`m_ToolBarDisabledImages`) списка изображений для `CToolBarCtrl` объекта (`m_ToolBarCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  Списки изображений, используемых объектом инструментов должен быть постоянными объектами. По этой причине они обычно представляют собой данные-члены класса MFC; в этом примере класс окна главного фрейма.  
  
 После связанных списков изображений с `CToolBarCtrl` объекта, платформа автоматически отображает значок соответствующие кнопки.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

