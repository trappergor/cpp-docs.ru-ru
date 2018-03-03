---
title: "Связи с древовидным элементом управления | Документы Microsoft"
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
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ef1188c9519e57c8132a2b20fc3b272d6c0ac51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления
Используют разные методы для вызова функций-членов [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект в зависимости от способа создания объекта:  
  
-   Если элемент управления дерева в диалоговом окне, использовать переменную-член типа `CTreeCtrl` , создаваемой в класс диалогового окна.  
  
-   Если дерево является дочерним окном, используйте `CTreeCtrl` объект (или указатель), используемый для создания объекта.  
  
-   Если вы используете `CTreeView` , используйте функцию [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) для получения ссылки на элементе управления иерархического представления. Можно инициализировать другую ссылку с помощью этого значения или назначить адреса ссылки для `CTreeCtrl` указателя.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

