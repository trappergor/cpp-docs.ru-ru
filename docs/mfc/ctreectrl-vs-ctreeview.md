---
title: CTreeCtrl vs. CTreeView | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71048b6f03f7f1b4400c0a88c178d1b97acdf2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl vs. CTreeView
MFC предоставляет две классов, которые инкапсулируют элементов управления древовидного типа: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md). Каждый класс полезен в различных ситуациях.  
  
 Используйте `CTreeCtrl` при необходимости plain дочернего окна элемента управления; например, в диалоговом окне. Особенно, следует использовать `CTreeCtrl` Если будут другие дочерние элементы управления в окне, как с обычным диалоговым окном.  
  
 Используйте `CTreeView` при необходимости дерева элементу управления действовать аналогично окно представления в архитектуры document/view, а также дерево объектов. Объект `CTreeView` займет всю клиентскую область фрейма окна или окна-разделителя. Он будет автоматически изменен при размера родительского окна, и она может обрабатывать сообщения команд из меню, панелей инструментов и сочетания клавиш. Поскольку дерево содержит данные, необходимые для отображения дерева, соответствующий объект документа не быть сложной, можно даже использовать [CDocument](../mfc/reference/cdocument-class.md) как тип документа в шаблоне документа.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

