---
title: Использование разворачивающихся кнопок в элемент управления Toolbar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e58b6b9d64111e021586fc23a985f31c0edf9de
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063774"
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

