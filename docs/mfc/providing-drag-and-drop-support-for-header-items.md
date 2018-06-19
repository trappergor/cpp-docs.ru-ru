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
ms.openlocfilehash: 50cd19d4828269d0591afd0b46768e9917b96906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349348"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Предоставление поддержки перетаскивания для элементов заголовка
Чтобы обеспечить поддержку и перетащите элементы заголовка, укажите `HDS_DRAGDROP` стиля. Поддержки перетаскивания и вставки для элементов заголовка дает пользователю возможность изменения порядка элементов заголовка элемента управления заголовка. Поведение по умолчанию предоставляет образ полупрозрачными перетащите перетаскиваемый элемент заголовка и визуальный индикатор новую позицию, при удалении элемента заголовка.  
  
 Как с общими функциональными возможностями и перетащите и перетащите поведение по умолчанию можно расширить путем обработки **HDN_BEGINDRAG** и **HDN_ENDDRAG** уведомления. Также можно настроить внешний вид изображение перетаскивания путем переопределения [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) функции-члена.  
  
> [!NOTE]
>  Если вы предоставляете поддержку и перетащите для элемента управления внедренных заголовка в элементе управления списком, в разделе расширенных стилей в [изменение стилей элемента управления "список"](../mfc/changing-list-control-styles.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

