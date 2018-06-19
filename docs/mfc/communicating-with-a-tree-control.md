---
title: Связи с древовидным элементом управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af0b248d5e32b535c23cc17b48efdd551dad7a2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342001"
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления
Используют разные методы для вызова функций-членов [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект в зависимости от способа создания объекта:  
  
-   Если элемент управления дерева в диалоговом окне, использовать переменную-член типа `CTreeCtrl` , создаваемой в класс диалогового окна.  
  
-   Если дерево является дочерним окном, используйте `CTreeCtrl` объект (или указатель), используемый для создания объекта.  
  
-   Если вы используете `CTreeView` , используйте функцию [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) для получения ссылки на элементе управления иерархического представления. Можно инициализировать другую ссылку с помощью этого значения или назначить адреса ссылки для `CTreeCtrl` указателя.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

