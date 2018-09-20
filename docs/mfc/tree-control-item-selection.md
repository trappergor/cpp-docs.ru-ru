---
title: Выбор элемента управления дерева | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa9c82a57ff8504c8e3eba7becff1e1cdccaae2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431571"
---
# <a name="tree-control-item-selection"></a>Выбор элемента древовидного элемента управления

При изменении выбора от одного элемента к другому, дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) и [TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) сообщений уведомления. Оба уведомления содержат значение, указывающее, находится ли изменение в результате щелчка кнопкой мыши или нажатие клавиши. Уведомления также содержат сведения о элемент, который приобретает все выделения и элемент, который теряет выделение. Эти сведения можно использовать для задания атрибутов элемента, которые зависят от состояния выбора элемента. Возвращение **TRUE** в ответ на `TVN_SELCHANGING` предотвращает изменение; Выбор возвращение **FALSE** разрешает изменение.

Выбор приложения можно изменить путем вызова [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) функция-член.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

