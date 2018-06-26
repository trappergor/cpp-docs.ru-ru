---
title: Предоставление поддержки перетаскивания и вставки для элементов заголовка | Документы Microsoft
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
ms.openlocfilehash: 6bf21021e204a6caf298453bab42db2aedff409c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928424"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Предоставление поддержки перетаскивания для элементов заголовка
Чтобы обеспечить поддержку и перетащите элементы заголовка, укажите hds_dragdrop-стиль. Поддержки перетаскивания и вставки для элементов заголовка дает пользователю возможность изменения порядка элементов заголовка элемента управления заголовка. Поведение по умолчанию предоставляет образ полупрозрачными перетащите перетаскиваемый элемент заголовка и визуальный индикатор новую позицию, при удалении элемента заголовка.  
  
 Как и с общими функциональными возможностями и перетащите можно расширить и перетащите поведение по умолчанию, обработка уведомлений HDN_BEGINDRAG и HDN_ENDDRAG. Также можно настроить внешний вид изображение перетаскивания путем переопределения [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) функции-члена.  
  
> [!NOTE]
>  Если вы предоставляете поддержку и перетащите для элемента управления внедренных заголовка в элементе управления списком, в разделе расширенных стилей в [изменение стилей элемента управления "список"](../mfc/changing-list-control-styles.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

