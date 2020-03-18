---
title: CTreeCtrl и CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 7c78dfa9920c913fdbedb009c5a6f275a3e3e273
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445231"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl и CTreeView

MFC предоставляет два класса, которые инкапсулируют элементы управления "дерево": [CTreeCtrl](../mfc/reference/ctreectrl-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md). Каждый класс полезен в различных ситуациях.

Используйте `CTreeCtrl`, если требуется обычный элемент управления дочернего окна; Например, в диалоговом окне. Особенно желательно использовать `CTreeCtrl`, если в окне есть другие дочерние элементы управления, как в типичном диалоговом окне.

Используйте `CTreeView`, если необходимо, чтобы элемент управления "дерево" действовал как окно представления в архитектуре "документ/представление", а также как элемент управления "дерево". `CTreeView` займет всю клиентскую область окна фрейма или окна-разделителя. Размер автоматически изменяется при изменении размера родительского окна и может обрабатывать сообщения команд из меню, клавиш быстрого вызова и панелей инструментов. Поскольку элемент управления "дерево" содержит данные, необходимые для вывода дерева, соответствующий объект документа не обязательно должен быть сложным — можно даже использовать [CDocument](../mfc/reference/cdocument-class.md) в качестве типа документа в шаблоне документа.

## <a name="see-also"></a>См. также раздел

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
