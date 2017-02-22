---
title: "Элементы управления и зоны главной панели | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "зоны, в элементах управления главной панели"
  - "Элементы управления главной панели, работа с лентами в"
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Элементы управления и зоны главной панели
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Основное назначение элемента управления "Главная панель" действовать как контейнер для дочерних элементов управления windows forms, стандартного диалогового окна печати, меню, панели инструментов и т д  Такая вложенность поддерживается понятием «полосы». Каждая полоса главной панели может содержать любую комбинацию панель захвата, растровое изображение, метка текстовой подписи и дочернее окно.  
  
 Класс `CReBarCtrl` имеет много функций\-членов, которые можно использовать для получения и управления, сведения о конкретной полосы главной панели:  
  
-   [GetBandCount](../Topic/CReBarCtrl::GetBandCount.md) Извлекает число текущих полос в элементе управления "Главная панель".  
  
-   [GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md) Инициализирует структуру **REBARBANDINFO** со сведениями из указанной полосы.  Соответствующую функцию\-член [SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md).  
  
-   [GetRect](../Topic/CReBarCtrl::GetRect.md) Возвращает ограничивающий прямоугольник определенной полосы.  
  
-   [GetRowCount](../Topic/CReBarCtrl::GetRowCount.md) Извлекает число строк полосы в элементе управления "Главная панель".  
  
-   [IDToIndex](../Topic/CReBarCtrl::IDToIndex.md) Извлекает индекс указанной полосы.  
  
-   [GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md) Возвращает границы полосы.  
  
 Помимо манипуляций нескольких функций\-членов, при условии, что разрешение, чтобы работать с конкретными полосы главной панели.  
  
 [InsertBand](../Topic/CReBarCtrl::InsertBand.md) [DeleteBand](../Topic/CReBarCtrl::DeleteBand.md) и добавлять и удалять полосы главной панели.  [MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)[MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md) и влияет текущий размер полосы определенной главной панели.  [MoveBand](../Topic/CReBarCtrl::MoveBand.md) изменить индекс определенной полосы главной панели.  [ShowBand](../Topic/CReBarCtrl::ShowBand.md) показывает или скрывает полосу главной панели от пользователя.  
  
 В следующем примере показано добавление полоса панели инструментов \(`m_wndToolBar`\) на существующий элемент управления "Главная панель" \(`m_wndReBar`\).  При инициализации полоса описана структура `rbi` и затем вызывать функцию\-член `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/CPP/rebar-controls-and-bands_1.cpp)]  
  
## См. также  
 [Использование CReBarCtrl](../Topic/Using%20CReBarCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)