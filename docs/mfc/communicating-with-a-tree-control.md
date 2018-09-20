---
title: Связи с древовидным элементом управления | Документация Майкрософт
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
ms.openlocfilehash: 78bb6a6d6421a5336f8efbffc7d24a6121e208e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432158"
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления

Использовать различные методы для вызова функций-членов [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект в зависимости от того, как был создан объект:

- Если элемент дерева в диалоговом окне, используйте переменную-член типа `CTreeCtrl` , создаваемый в класса диалогового окна.

- Если дерево дочернего окна, используйте `CTreeCtrl` объект (или указатель), используемый для создания объекта.

- Если вы используете `CTreeView` , используйте функцию [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) для получения ссылки на дерево. Можно инициализировать другую ссылку с этим значением или назначить адрес ссылки для `CTreeCtrl` указатель.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

