---
title: Установка связи с древовидным элементом управления
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 920608724ebb362b91efdcb3eab50b80acd20474
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289888"
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления

Использовать различные методы для вызова функций-членов [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект в зависимости от того, как был создан объект:

- Если элемент дерева в диалоговом окне, используйте переменную-член типа `CTreeCtrl` , создаваемый в класса диалогового окна.

- Если дерево дочернего окна, используйте `CTreeCtrl` объект (или указатель), используемый для создания объекта.

- Если вы используете `CTreeView` , используйте функцию [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) для получения ссылки на дерево. Можно инициализировать другую ссылку с этим значением или назначить адрес ссылки для `CTreeCtrl` указатель.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
