---
title: "Сведения об элементе древовидного элемента управления | Microsoft Docs"
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
  - "CTreeCtrl - класс, сведения об элементе"
  - "элементы управления "дерево", сведения об элементе"
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сведения об элементе древовидного элемента управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элементы управления дерева \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\), имеют несколько функций\-членов извлекает сведения об элементах в элементе управления.  Функцию\-член [GetItem](../Topic/CTreeCtrl::GetItem.md) извлекает некоторые или все данные, связанные с элементом.  Эта информация может содержать текст элемента, состояний, изображения, число дочерних элементов и приложением, значение 32 — данные.  Также функция [SetItem](../Topic/CTreeCtrl::SetItem.md), которая может задать некоторые или все данные, связанные с элементом.  
  
 [GetItemState](../Topic/CTreeCtrl::GetItemState.md), [GetItemText](../Topic/CTreeCtrl::GetItemText.md), [GetItemData](../Topic/CTreeCtrl::GetItemData.md) и [GetItemImage](../Topic/CTreeCtrl::GetItemImage.md) функции\-члены извлекают отдельные атрибуты элемента.  Каждая из этих функций имеет соответствующий набора функций для параметра атрибуты элемента.  
  
 Функцию\-член [GetNextItem](../Topic/CTreeCtrl::GetNextItem.md) извлекает элемент управления "Дерево", передает определенного отношения к текущему элементу.  Эта функция может получить родительский элемент, или в предыдущий видимый элемент, первый дочерний элемент, и т д  Также функции\-члены для обхода дерева: [GetRootItem](../Topic/CTreeCtrl::GetRootItem.md), [GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md), [GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md), [GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md), [GetChildItem](../Topic/CTreeCtrl::GetChildItem.md), [GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md), [GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md), [GetParentItem](../Topic/CTreeCtrl::GetParentItem.md), [GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md) и [GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md).  
  
 Функцию\-член [GetItemRect](../Topic/CTreeCtrl::GetItemRect.md) возвращает ограничивающий прямоугольник для элемента управления дерева.  Функции\-члены [GetCount](../Topic/CTreeCtrl::GetCount.md) и [GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md) возвращают число элементов в элементе управления дерева и количество элементов, которые в данный момент видимым в окне элемента управления "Дерево" соответственно.  Можно предоставить, что указанный элемент видимым, вызвав функцию\-член [EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md).  
  
## См. также  
 [Использование CTreeCtrl](../Topic/Using%20CTreeCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)