---
title: Установка связи с древовидным элементом управления
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: a5749b76468a7ba30cd48dc3a9b61f2de7ac67b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654194"
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления

Использовать различные методы для вызова функций-членов [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект в зависимости от того, как был создан объект:

- Если элемент дерева в диалоговом окне, используйте переменную-член типа `CTreeCtrl` , создаваемый в класса диалогового окна.

- Если дерево дочернего окна, используйте `CTreeCtrl` объект (или указатель), используемый для создания объекта.

- Если вы используете `CTreeView` , используйте функцию [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) для получения ссылки на дерево. Можно инициализировать другую ссылку с этим значением или назначить адрес ссылки для `CTreeCtrl` указатель.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

