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
ms.openlocfilehash: 8d1a13b1921f111d97bb515e7932a0116277f9ed
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261047"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Использование разворачивающихся кнопок в элементе управления панели инструментов

Помимо стандартных кнопок панели инструментов могут также иметь кнопки раскрывающегося списка. Кнопка раскрывающегося списка обычно определяется наличие присоединенных вниз стрелки.

> [!NOTE]
>  Вложенные вниз стрелка будет отображаться только в том случае, если задана TBSTYLE_EX_DRAWDDARROWS расширенный стиль.

Когда пользователь выбирает эту стрелку, (или самой, при наличии не стрелку кнопки), сообщение уведомления TBN_DROPDOWN отправляется родителю элемента управления панели инструментов. Затем можно обработать это уведомление и отображения всплывающего меню; аналогично поведению обозревателя Internet Explorer.

В следующей процедуре показано, как реализовать с помощью всплывающего меню кнопки раскрывающегося списка:

### <a name="to-implement-a-drop-down-button"></a>Реализация кнопки раскрывающегося списка

1. Один раз в `CToolBarCtrl` объект был создан, задать стиль TBSTYLE_EX_DRAWDDARROWS, используя следующий код:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. Задать стиль TBSTYLE_DROPDOWN для любых новых ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) или [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) или имеющиеся ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) кнопок, разворачивающихся кнопок. В следующем примере показано изменение существующую кнопку в `CToolBarCtrl` объекта:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Добавьте обработчик TBN_DROPDOWN в родительский класс объекта панели инструментов.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. В новый обработчик отобразить соответствующее меню. Следующий код демонстрирует один метод:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>См. также

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
