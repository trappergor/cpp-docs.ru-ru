---
title: Использование разворачивающихся кнопок в элементе управления панели инструментов
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: 0bc4df4c07ec4b8bc5b488925cbb140609302186
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365067"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Использование разворачивающихся кнопок в элементе управления панели инструментов

В дополнение к стандартным кнопкам нажатия, панель инструментов может также иметь кнопки выпадения вниз. Кнопка выпадения обычно указывается наличием прикрепленной вниз стрелки.

> [!NOTE]
> Прикрепленная стрелка появится только в том случае, если установлен TBSTYLE_EX_DRAWDDARROWS расширенный стиль.

Когда пользователь нажимает на эту стрелку (или на саму кнопку, если стрелки нет), TBN_DROPDOWN сообщение уведомления отправляется родительскому элементу управления панели инструментов. Затем вы можете обрабатывать это уведомление и отображать всплывающее меню; аналогично поведению Internet Explorer.

Следующая процедура иллюстрирует, как реализовать кнопку панели инструментов с выпадающим плат с всплывающее меню:

### <a name="to-implement-a-drop-down-button"></a>Реализация кнопки выпадения

1. Как `CToolBarCtrl` только объект создан, установите TBSTYLE_EX_DRAWDDARROWS стиль, используя следующий код:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. Установите стиль TBSTYLE_DROPDOWN для любых новых[(InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) или [AddButtons)](../mfc/reference/ctoolbarctrl-class.md#addbuttons)или существующих ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) кнопки, которые будут выпадающие кнопки. Следующий пример демонстрирует изменение существующей `CToolBarCtrl` кнопки в объекте:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Добавьте обработчик TBN_DROPDOWN в родительский класс объекта панели инструментов.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. В новом обработчике отобразите соответствующее всплывающее меню. Следующий код демонстрирует один метод:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
