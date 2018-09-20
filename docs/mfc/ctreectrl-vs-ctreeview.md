---
title: CTreeCtrl или CTreeView | Документация Майкрософт
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
ms.openlocfilehash: e8acaecbdfb99b8ae0b27023145a0ef6aee1f219
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399155"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl или CTreeView

MFC предоставляет два класса, которые инкапсулируют элементов управления древовидного типа: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md). Каждый класс можно использовать в различных ситуациях.

Используйте `CTreeCtrl` при необходимости plain дочернего элемента управления окна; например, в диалоговом окне. Особенно следует использовать `CTreeCtrl` в случае использования других дочерних элементов управления в окне, как показано типичного диалогового окна.

Используйте `CTreeView` при необходимости дерево будет работать как в окно представления в архитектуры document/view, а также дерево. Объект `CTreeView` займет всей клиентской области окна фрейма или окна разделителя. Он будет автоматически изменяться при изменении размера родительского окна, и он мог обрабатывать сообщения команды из меню, панелей инструментов и сочетания клавиш. Поскольку дерево содержит данные, необходимые для отображения дерева, соответствующий объект документа не быть сложным, можно даже использовать [CDocument](../mfc/reference/cdocument-class.md) как тип документа в шаблоне документа.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

