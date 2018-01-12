---
title: "CTreeCtrl vs. CTreeView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs: C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb0c1b7a7bf73ab70bbccca6f2a9ccc2ab385516
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl vs. CTreeView
MFC предоставляет две классов, которые инкапсулируют элементов управления древовидного типа: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md). Каждый класс полезен в различных ситуациях.  
  
 Используйте `CTreeCtrl` при необходимости plain дочернего окна элемента управления; например, в диалоговом окне. Особенно, следует использовать `CTreeCtrl` Если будут другие дочерние элементы управления в окне, как с обычным диалоговым окном.  
  
 Используйте `CTreeView` при необходимости дерева элементу управления действовать аналогично окно представления в архитектуры document/view, а также дерево объектов. Объект `CTreeView` займет всю клиентскую область фрейма окна или окна-разделителя. Он будет автоматически изменен при размера родительского окна, и она может обрабатывать сообщения команд из меню, панелей инструментов и сочетания клавиш. Поскольку дерево содержит данные, необходимые для отображения дерева, соответствующий объект документа не быть сложной, можно даже использовать [CDocument](../mfc/reference/cdocument-class.md) как тип документа в шаблоне документа.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

