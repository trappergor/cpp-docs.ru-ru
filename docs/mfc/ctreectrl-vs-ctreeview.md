---
title: CTreeCtrl и CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 83e07c75b9eab6df05dbcd0f52cfbe8b90e1d768
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620485"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl и CTreeView

MFC предоставляет два класса, которые инкапсулируют элементы управления "дерево": [CTreeCtrl](reference/ctreectrl-class.md) и [CTreeView](reference/ctreeview-class.md). Каждый класс полезен в различных ситуациях.

Используется `CTreeCtrl` , если требуется обычный элемент управления "дочернее окно"; например, в диалоговом окне. Особенно желательно использовать `CTreeCtrl` , если в окне есть другие дочерние элементы управления, как в обычном диалоговом окне.

Используется, если необходимо, `CTreeView` чтобы элемент управления "дерево" действовал как окно представления в архитектуре "документ/представление", а также как элемент управления "дерево". `CTreeView`Будет занимать всю клиентскую область окна фрейма или окна-разделителя. Размер автоматически изменяется при изменении размера родительского окна и может обрабатывать сообщения команд из меню, клавиш быстрого вызова и панелей инструментов. Поскольку элемент управления "дерево" содержит данные, необходимые для вывода дерева, соответствующий объект документа не обязательно должен быть сложным — можно даже использовать [CDocument](reference/cdocument-class.md) в качестве типа документа в шаблоне документа.

## <a name="see-also"></a>См. также раздел

[Использование CTreeCtrl](using-ctreectrl.md)<br/>
[Элементы управления](controls-mfc.md)
