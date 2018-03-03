---
title: "Выбор элемента управления дерева | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b38761b27c21dcf0fe3118d5b73e104cbaaa673d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-selection"></a>Выбор элемента древовидного элемента управления
При изменении выбора одного элемента к другому дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) и [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) сообщений уведомления. Оба уведомления содержат значение, указывающее, является ли изменения в результате щелчка кнопкой мыши или нажатие клавиши. Уведомления также содержат сведения о элемента, которая получает выделение и элемент, который теряет выделение. Эти сведения можно использовать для задания атрибутов элемента, зависящих от состояния выбора элемента. Возвращение **TRUE** в ответ на **TVN_SELCHANGING** предотвращает изменение; Выбор возвращение **FALSE** можно изменить.  
  
 Этот выбор можно изменить приложение, вызвав [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

