---
title: Древовидная метки элемента управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e016093e2dcde68fcc01691c4877841d648321fb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207468"
---
# <a name="tree-control-item-labels"></a>Метки элементов древовидного элемента управления
Текст метки элемента обычно указывается при добавлении элемента в элементе управления иерархического ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem` Можно передать функции-члена [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) структура, определяющая свойства элемента, включая строку, содержащую текст метки. `InsertItem` имеет несколько перегрузок, которые могут вызываться с различными сочетаниями параметров.  
  
 Дерево выделяет память для хранения каждого элемента; текст метки элемента занимает значительную часть этой памяти. Если приложение сохраняет копию строки в элементе управления иерархического представления, можно уменьшить потребление памяти при выполнении элемента управления путем указания **LPSTR_TEXTCALLBACK** значение в *pszText* членом `TV_ITEM` или *lpszItem* параметра вместо того чтобы передавать фактические строки в элементе управления иерархического представления. С помощью **LPSTR_TEXTCALLBACK** элемент извлечь текст метки элемента из приложения, при необходимости перерисовки элемента управления дерева. Для получения текста, отправляет дерево [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) сообщения уведомления, которое включает адрес [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) структуры. Вы должны ответить, задав соответствующие члены структуры, включены.  
  
 Дерево использует память из кучи процесса, который создает дерево. Максимальное число элементов в элементе дерева зависит объем памяти в куче. Каждый элемент занимает 64 байта.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

