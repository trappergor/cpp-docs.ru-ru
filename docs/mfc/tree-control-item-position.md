---
title: "Положение элемента управления дерева | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db47e27ad0b556e08f51685bf84b6bd998722239
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-position"></a>Положение элемента древовидного элемента управления
Начальное положение элемента имеет значение при добавлении элемента управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) с помощью `InsertItem` функции-члена. Вызова функции-члена задает дескриптор родительского элемента и дескриптор элементом, после которого вставляется новый элемент. Необходимо определить, дескриптор второй дочерний элемент данного родительского элемента или одно из этих значений: `TVI_FIRST`, `TVI_LAST`, или `TVI_SORT`.  
  
 Когда `TVI_FIRST` или `TVI_LAST` указан, дерево размещает новый элемент в начале или в конце списка дочерних элементов данного родительского элемента. Когда `TVI_SORT` указан, дерево вставляет новый элемент в список дочерних элементов в алфавитном порядке на основе текста метки элемента.  
  
 Можно поместить в алфавитном порядке списка дочерних элементов родительского элемента, вызвав [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) функции-члена. Эта функция включает параметр, указывающий, является ли всех уровней дочерних элементов по убыванию, от данного родительского элемента также сортируются в алфавитном порядке.  
  
 [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) функция-член позволяет сортировать на основе критериев, которые указываются в дочерних элементов. При вызове этой функции необходимо указать функцию обратного вызова, определяемые приложением, можно вызвать в элементе управления иерархического представления всякий раз, когда необходимо принять решение относительного порядка двух дочерних элементов. Функция обратного вызова получает два 32-разрядных определяемые приложением значения сравниваемых элементов и третий 32-разрядное значение, указываемое при вызове `SortChildrenCB`.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

