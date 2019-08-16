---
title: Выбор элемента древовидного элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 07c7b673e0f9029f8ece928b0ab17760b3863cc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513336"
---
# <a name="tree-control-item-selection"></a>Выбор элемента древовидного элемента управления

Когда выбор изменяется от одного элемента к другому, элемент управления "дерево" ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет сообщения уведомления [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) и [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) . Оба уведомления включают значение, указывающее, является ли изменение результатом щелчка мыши или нажатия клавиши. Уведомления также содержат сведения об элементе, который получает выделение, и элементе, который теряет выделение. Эти сведения можно использовать для задания атрибутов элементов, зависящих от состояния выбора элемента. При возврате значения true `TVN_SELCHANGING` в ответе предотвращается изменение выбора; возврат значения **false** позволяет изменить.

Приложение может изменить выбор, вызвав функцию члена [селектитем](../mfc/reference/ctreectrl-class.md#selectitem) .

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
