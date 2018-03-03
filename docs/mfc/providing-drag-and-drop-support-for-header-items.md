---
title: "Предоставление поддержки перетаскивания и вставки для элементов заголовка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd1ac2171a13610ee3aeabed12f5348089a57491
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Предоставление поддержки перетаскивания для элементов заголовка
Чтобы обеспечить поддержку и перетащите элементы заголовка, укажите `HDS_DRAGDROP` стиля. Поддержки перетаскивания и вставки для элементов заголовка дает пользователю возможность изменения порядка элементов заголовка элемента управления заголовка. Поведение по умолчанию предоставляет образ полупрозрачными перетащите перетаскиваемый элемент заголовка и визуальный индикатор новую позицию, при удалении элемента заголовка.  
  
 Как с общими функциональными возможностями и перетащите и перетащите поведение по умолчанию можно расширить путем обработки **HDN_BEGINDRAG** и **HDN_ENDDRAG** уведомления. Также можно настроить внешний вид изображение перетаскивания путем переопределения [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) функции-члена.  
  
> [!NOTE]
>  Если вы предоставляете поддержку и перетащите для элемента управления внедренных заголовка в элементе управления списком, в разделе расширенных стилей в [изменение стилей элемента управления "список"](../mfc/changing-list-control-styles.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

