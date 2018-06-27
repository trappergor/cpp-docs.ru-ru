---
title: Метки элемента управления дерева | Документы Microsoft
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
ms.openlocfilehash: 3fc207dcff5002262c345b106be99a775ed626b9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953730"
---
# <a name="tree-control-item-labels"></a>Метки элементов древовидного элемента управления
Обычно указывается текст метки элемента при добавлении элемента в элементе управления иерархического представления ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem` Можно передать функции-члена [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структура, определяющая свойства элемента, включая строка, содержащая текст метки. `InsertItem` есть несколько перегрузок, которые могут быть вызваны с различными сочетаниями параметров.  
  
 Структура дерева выделяет память для хранения каждого элемента; текст метки элемента будет занимать значительную часть этой памяти. Если приложение сохраняет копию строки в элементе управления иерархического представления, можно уменьшить требования к памяти элемента управления, указав **LPSTR_TEXTCALLBACK** значение в *pszText* членом `TV_ITEM` или *lpszItem* параметра вместо передачи фактических строк в элементе управления иерархического представления. С помощью **LPSTR_TEXTCALLBACK** элемент управления для получения текста метки элемента из приложения, при необходимости перерисовки элемента дерева. Для получения текста, отправляет дерево [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) сообщение уведомления, включая адрес [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) структуры. Вы должны ответить, задав соответствующие члены структуры включены.  
  
 Структура дерева использует память, выделенную из кучи процесса, который создает дерево. Максимальное количество элементов в виде дерева зависит объем памяти в куче. Каждый элемент занимает 64 байта.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

