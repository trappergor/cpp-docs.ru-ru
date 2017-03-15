---
title: "Использование разворачивающихся кнопок в элементе управления панели инструментов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBN_DROPDOWN"
  - "TBSTYLE_EX_DRAWDDARROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl - класс, кнопки раскрытия списка"
  - "кнопки раскрытия списка на панелях инструментов"
  - "TBN_DROPDOWN - уведомление"
  - "TBSTYLE_EX_DRAWDDARROWS"
  - "панели инструментов [C++], кнопки раскрытия списка"
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Использование разворачивающихся кнопок в элементе управления панели инструментов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В дополнение к стандартным кнопок панели инструментов, также может использовать кнопки со списком.  Разворачивающуюся кнопку обычно отображается наличием вложенное вниз стрелки.  
  
> [!NOTE]
>  Вложенное вниз стрелки появится только в том случае, если установлен расширенный стиль `TBSTYLE_EX_DRAWDDARROWS`.  
  
 Когда пользователь щелкнет эта стрелка \(или кнопку сама, если нет стрелку отсутствует\), сообщение уведомления `TBN_DROPDOWN` отправляется к родительскому элементу управления панели инструментов.  Затем можно обработать это уведомление и отобразить контекстное меню меню; аналогично расширение функциональности Internet Explorer.  
  
 В следующей процедуре показано, как реализовать кнопки панели инструментов падающую вниз с всплывающим меню:  
  
### Реализация кнопки со списком  
  
1.  После создания объект `CToolBarCtrl` создан, задать стиль `TBSTYLE_EX_DRAWDDARROWS`, используя следующий код:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Задать стиль `TBSTYLE_DROPDOWN` для всех новых \([InsertButton](../Topic/CToolBarCtrl::InsertButton.md) или [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)\) или существующие кнопок \([SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)\), которые будут кнопки со списком.  В следующем примере демонстрируется изменение существующей кнопку в объекте `CToolBarCtrl`:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Добавьте обработчик `TBN_DROPDOWN` в родительский класс объекта инструмента.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  В новый обработчик, откройте соответствующее контекстное меню меню.  Следующий код демонстрирует один метод:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)