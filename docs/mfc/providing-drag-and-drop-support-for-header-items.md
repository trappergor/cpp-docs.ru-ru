---
title: Предоставление поддержки перетаскивания и вставки для элементов заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2eaa5040d34a442868a8fa6cb9f2aae08b0a6f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407703"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Предоставление поддержки перетаскивания для элементов заголовка

Для обеспечения поддержки перетаскивания и вставки для элементов заголовка, укажите hds_dragdrop-стиль. Поддержка и перетащите для элементов заголовка предоставляет пользователю возможность изменения порядка элементов заголовка элемента управления заголовка. Поведение по умолчанию предоставляет изображение полупрозрачные компоненты перетаскивания элемента заголовка перетаскиваемого и визуальным индикатором новое положение, если удаляется элемент заголовка.

Как и с общими функциональными возможностями перетаскивания и вставки, можно расширить и перетащите поведение по умолчанию, обработка уведомлений HDN_BEGINDRAG и HDN_ENDDRAG. Также можно настроить внешний вид изображение перетаскивания путем переопределения [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) функция-член.

> [!NOTE]
>  Если вы предоставляете поддержку перетаскивания и вставки для элемента управления внедренных заголовка в элементе управления списком, см. в разделе расширенных стилей в [изменение стилей элемента управления "список"](../mfc/changing-list-control-styles.md) раздела.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

