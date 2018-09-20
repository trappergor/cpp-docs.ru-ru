---
title: Использование списков изображений в элемент управления Toolbar | Документация Майкрософт
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
ms.openlocfilehash: c3604de0b3b24b638e549c6823ea6c95036543c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401775"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Использование списков изображений в элементе управления панели инструментов

По умолчанию изображения, используемые кнопок в элемент управления toolbar хранятся как одном точечном рисунке. Тем не менее можно также хранить изображения кнопки в набор списков изображений. Объект элемента управления панели инструментов можно использовать до трех списков отдельный образ:

- Включить изображение списка Contains, изображения для кнопки панели инструментов, доступных в настоящее время.

- Отключить вывод списка образов Contains на изображения для кнопки панели инструментов, который в настоящее время отключены.

- Выделено изображение списка Contains, изображения для кнопки панели инструментов, который в данный момент выделены. Этот список изображений используется только в том случае, если панель инструментов использует стиль TBSTYLE_FLAT.

Эти списки изображений используются элементом управления панели инструментов, при связывании их с помощью `CToolBarCtrl` объекта. Это сопоставление выполняется с помощью обращений к [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), и [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).

По умолчанию использует MFC `CToolBar` класс для реализации панелей инструментов приложения MFC. Тем не менее `GetToolBarCtrl` функция-член можно использовать для получения внедренный `CToolBarCtrl` объекта. Вы можете затем вызывать `CToolBarCtrl` функций-членов с помощью возвращенного объекта.

В следующем примере демонстрируется этот метод, назначив активный (`m_ToolBarImages`) и отключен (`m_ToolBarDisabledImages`) список изображений для `CToolBarCtrl` объекта (`m_ToolBarCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
>  Списки изображений, используемых объектом инструментов должен быть постоянными объектами. По этой причине, они обычно являются данные-члены класса MFC; в этом примере класс окна главного фрейма.

После связанных списков изображений с `CToolBarCtrl` объекта, платформа автоматически отображает изображение соответствующие кнопки.

## <a name="see-also"></a>См. также

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

