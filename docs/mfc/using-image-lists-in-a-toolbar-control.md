---
title: Использование списков изображений в элементе управления панели инструментов
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: 81468528c15300a7e9ace6b20fd9fb34818f1928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366499"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Использование списков изображений в элементе управления панели инструментов

По умолчанию изображения, используемые кнопками в панели инструментов управления хранятся в виде одной битовой карты. Тем не менее, вы также можете хранить изображения кнопок в наборе списков изображений. Объект управления панелью инструментов может использовать до трех отдельных списков изображений:

- Включенный список изображений содержит изображения для кнопок панели инструментов, которые в настоящее время включены.

- Список изображений отключенных содержит изображения для кнопок панели инструментов, которые в настоящее время отключены.

- Выделенный список изображений содержит изображения для кнопок панели инструментов, которые в настоящее время выделены. Этот список изображений используется только тогда, когда панель инструментов использует TBSTYLE_FLAT стиль.

Эти списки изображений используются управлением панели `CToolBarCtrl` инструментов при их связывании с объектом. Эта ассоциация достигается путем звонков на [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), и [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).

По умолчанию MFC `CToolBar` использует класс для реализации инструментов приложений MFC. Тем не `GetToolBarCtrl` менее, функция члена может `CToolBarCtrl` быть использована для извлечения встроенного объекта. Затем можно совершать `CToolBarCtrl` звонки на функции членов с помощью возвращенного объекта.

Следующий пример демонстрирует этот метод, назначив`m_ToolBarImages`включенному`m_ToolBarDisabledImages`( ) `CToolBarCtrl` и отключенному () список изображений объекту ().`m_ToolBarCtrl`

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> Списки изображений, используемые объектом панели инструментов, должны быть постоянными объектами. По этой причине они обычно являются членами данных класса MFC; в этом примере, основной класс окна кадра.

После того, как списки изображений связаны с объектом, `CToolBarCtrl` фреймворк автоматически отображает соответствующее изображение кнопки.

## <a name="see-also"></a>См. также раздел

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
