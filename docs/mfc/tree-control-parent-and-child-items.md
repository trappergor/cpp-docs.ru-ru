---
title: "Родительский элемент управления и дочерние элементы древовидного | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6fa3efc37b251024feae79343ddfbd51769c7d53
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-parent-and-child-items"></a>Родительские и дочерние элементы древовидного элемента управления
Любой элемент в виде дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) может содержать список элементов, которые называются дочерние элементы, связанные с ним. Элемент, имеющий один или несколько дочерних элементов вызывается с родительским элементом. Дочерний элемент отображается под его родительским элементом и с отступом, чтобы указать, что он является подчиненным для родительского. Элемент, который не имеет родителя в верхней части иерархии и вызывается корневой элемент.  
  
 В любой момент времени состояние списка дочерних элементов родительского элемента можно либо разворачивать и сворачивать. При разворачивании состояния дочерних элементов отображаются под родительским элементом. Если он свернут, дочерние элементы не отображаются. Список автоматически переключает между развернутым и свернутым состояниями при двойном щелчке родительского элемента или, если родитель имеет **TVS_HASBUTTONS** стиль, при нажатии кнопки, связанной с родительским элементом. Приложение можно развернуть или свернуть дочерние элементы с помощью [развернуть](../mfc/reference/ctreectrl-class.md#expand) функции-члена.  
  
 Добавить элемент в дерево путем вызова [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) функции-члена. Эта функция возвращает дескриптор **HTREEITEM** тип, который однозначно определяет элемент. При добавлении элемента, необходимо указать дескриптор родительского элемента нового элемента. При указании **NULL** или **TVI_ROOT** значение, а не дескриптор родительского элемента в [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) структуры или `hParent` параметра, элемент добавляется в качестве корня элемент.  
  
 Структура дерева отправляет [TVN_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) уведомление при намерении разворачивать и сворачивать с родительским элементом списка дочерних элементов. Уведомление предоставляют возможность для предотвращения изменения или задания все атрибуты родительского элемента, которые зависят от состояния списка дочерних элементов. После изменения состояния списка, дерева отправляет [TVN_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533) сообщение уведомления.  
  
 При развертывании списка дочерних элементов, делается отступ относительно родительского элемента. Можно задать величину отступа с помощью [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) функции-члена или извлечь текущий объем с помощью [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

