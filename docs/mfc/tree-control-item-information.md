---
title: "Сведения об элементе управления древовидной | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16e4a707c4bc1f0fde76ab3a146424d2d34d5ec8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-information"></a>Сведения об элементе древовидного элемента управления
Элементы управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) имеют ряд функций-членов, получающие сведения о элементов в элементе управления. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) функция-член возвращает некоторые или все данные, связанные с элементом. Эти данные могут включать текст элемента, состояние, изображений, количество дочерних элементов и прикладных данных 32-разрядное значение. Имеется также [SetItem](../mfc/reference/ctreectrl-class.md#setitem) функцию, которая может устанавливать некоторые или все данные, связанные с элементом.  
  
 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), и [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) функции-члены получить отдельные атрибуты элемент. Каждая из этих функций имеет соответствующий набор функцию для настройки атрибутов элемента.  
  
 [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) функция-член возвращает дерево элемента управления, содержащим указанную связь с текущим элементом. Эта функция может получить родительский элемент, следующий или предыдущий элемент видимым, первый дочерний элемент и т. д. Существуют также функции-члены для прохода по дереву: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), и [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).  
  
 [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) функция-член Возвращает ограничивающий прямоугольник для элемента управления дерева. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) и [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) функции-члены получить количество элементов в виде дерева и количество элементов, видимых в настоящее время в окне элемента управления дерева соответственно. Убедитесь, что какой-либо элемент является видимым, вызвав [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

