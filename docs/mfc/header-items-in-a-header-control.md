---
title: Элементы заголовка в элементе управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], header items in
- header items in header controls [MFC]
- CHeaderCtrl class [MFC], header items in
- controls [MFC], header
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21f1893861c5cb6a134cffa75806cc53eadaf059
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442374"
---
# <a name="header-items-in-a-header-control"></a>Элементы заголовка в элементе управления "Заголовок"

У вас есть много возможностей управления внешним видом и поведением элементов заголовка, составляющие элемент управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)). Каждый элемент заголовка может иметь строку, растровый рисунок, образ из списка связанных изображений или связанные с ним значение 32-разрядных определяемые приложением. Строка, растрового изображения или изображения отображаются в верхнем колонтитуле.

Можно настроить внешний вид и содержимое новых элементов, когда они создаются путем вызова [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem) или путем изменения существующего элемента, с помощью вызова [CHeaderCtrl::GetItem](../mfc/reference/cheaderctrl-class.md#getitem) и [ CHeaderCtrl::SetItem](../mfc/reference/cheaderctrl-class.md#setitem).

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Настройка внешнего вида элемента заголовка](../mfc/customizing-the-header-item-s-appearance.md)

- [Сортировка элементов в элементе управления заголовка](../mfc/ordering-items-in-the-header-control.md)

- [Предоставление поддержки перетаскивания и вставки для элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md)

- [Использование списков изображений с элементами управления заголовка](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

