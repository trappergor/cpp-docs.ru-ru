---
title: Выбор элемента управления дерева | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb08fcbb1bd77cc80fdbe014d8c9e8a0851254d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-selection"></a>Выбор элемента древовидного элемента управления
При изменении выбора одного элемента к другому дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) и [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) сообщений уведомления. Оба уведомления содержат значение, указывающее, является ли изменения в результате щелчка кнопкой мыши или нажатие клавиши. Уведомления также содержат сведения о элемента, которая получает выделение и элемент, который теряет выделение. Эти сведения можно использовать для задания атрибутов элемента, зависящих от состояния выбора элемента. Возвращение **TRUE** в ответ на **TVN_SELCHANGING** предотвращает изменение; Выбор возвращение **FALSE** можно изменить.  
  
 Этот выбор можно изменить приложение, вызвав [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

