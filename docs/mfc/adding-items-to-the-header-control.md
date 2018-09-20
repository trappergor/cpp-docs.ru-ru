---
title: Добавление элементов управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0eb06a15cac87b063ada1cbe8f130b3464be0b0a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447184"
---
# <a name="adding-items-to-the-header-control"></a>Добавление элементов в элемент управления "Заголовок"

После создания элемента управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) в его родительского окна, добавьте «заголовка произвольное число условий фильтра» необходимо: обычно по одному на столбец.

### <a name="to-add-a-header-item"></a>Чтобы добавить элемент заголовка

1. Подготовка [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуры.

1. Вызовите [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), передачи структуры.

1. Повторите шаги 1 и 2 для дополнительных элементов.

Дополнительные сведения см. в разделе [Добавление элемента управления заголовка](/windows/desktop/Controls/header-controls) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

