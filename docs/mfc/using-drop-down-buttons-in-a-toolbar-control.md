---
title: Использование разворачивающихся кнопок в элементе управления панели инструментов | Документы Microsoft
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
ms.openlocfilehash: 39edda143e28d262e8eea826ced5c24855fb310b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Использование разворачивающихся кнопок в элементе управления панели инструментов
Помимо стандартных кнопок панели инструментов могут также иметь разворачивающихся кнопок. Кнопка раскрывающегося списка, обычно определяется наличие вложенных вниз стрелки.  
  
> [!NOTE]
>  Вложенные вниз стрелку будут отображаться только в том случае, если `TBSTYLE_EX_DRAWDDARROWS` задан расширенный стиль.  
  
 При нажатии на эту стрелку (или самой при наличии нет стрелки кнопки), `TBN_DROPDOWN` с родительским элементом управления панели инструментов отправляется уведомление. Затем можно обработать это уведомление и отображения во всплывающем меню. аналогично поведению обозревателя Internet Explorer.  
  
 В следующей процедуре показано, как реализовать кнопки раскрывающегося списка с помощью всплывающего меню:  
  
### <a name="to-implement-a-drop-down-button"></a>Реализация кнопки раскрывающегося списка  
  
1.  Один раз на `CToolBarCtrl` создан объект, задайте `TBSTYLE_EX_DRAWDDARROWS` стиля, используя следующий код:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Задать `TBSTYLE_DROPDOWN` стиль для любых новых ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) или [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) или имеющиеся ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) кнопок, разворачивающихся кнопок. В следующем примере показано изменение существующую кнопку в `CToolBarCtrl` объекта:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Добавить `TBN_DROPDOWN` обработчик родительский класс объекта панели инструментов.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  В новый обработчик отображают соответствующие всплывающего меню. Следующий код демонстрирует один из методов:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

