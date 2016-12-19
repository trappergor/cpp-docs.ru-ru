---
title: "Элемент управления &quot;Список&quot; и представление списка | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl - класс, и CListView"
  - "CListView - класс, и CListCtrl"
  - "Список - элементы управления, представления списков"
  - "представления списков"
  - "представления, список и элемент управления "список""
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Элемент управления &quot;Список&quot; и представление списка
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для удобства в MFC инкапсулирует элемента управления "Список" в 2 вариантах.  Можно использовать элементы управления "Список".  
  
-   Напрямую, путем включения объект [CListCtrl](../Topic/CListCtrl%20Class.md) в классе диалогового окна.  
  
-   Косвенным образом с помощью класса [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView` упрощает интегрировать элемент управления "Список" документ\/представление архитектура с MFC, инкапсулируя элемент управления много как [CEditView](../Topic/CEditView%20Class.md) инкапсулирует элемента управления "Поле ввода": элемент управления заполняют всю контактную зону представлений MFC. \(Представление элемента управления, приведение к `CListView`\).  
  
 Объект `CListView` наследуется от [CCtrlView](../mfc/reference/cctrlview-class.md) и его базовых классов и добавляет функцию\-член для извлечения основной элемент управления "Список".  Используйте члены представления для работы с представлением в качестве представления.  Используйте функции\-члена [GetListCtrl](../Topic/CListView::GetListCtrl.md), чтобы получить доступ к функциям элемента элемента управления "Список".  Эти члены.  
  
-   Добавлять, удалять или изменять элементы «» в списке.  
  
-   Задать или получить атрибуты элемента управления "Список".  
  
 Для получения ссылки на `CListCtrl` основного `CListView` в основе, вызовите `GetListCtrl` из класса представления списка:  
  
 [!code-cpp[NVC_MFCListView#4](../mfc/codesnippet/CPP/list-control-and-list-view_1.cpp)]  
  
 В этом разделе описываются оба способа использования элемента управления "Список".  
  
## См. также  
 [Использование CListCtrl](../Topic/Using%20CListCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)