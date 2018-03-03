---
title: "Элементы обратного вызова и маска обратного вызова | Документы Microsoft"
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
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24d9992b8a9db679b30624d85ede1a35bfd9826d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="callback-items-and-the-callback-mask"></a>Элементы обратного вызова и маска обратного вызова
Для каждого из его элементов элементе представления списка обычно хранят текст метки, индекс списка изображения значков для элемента, и набор бит флаги для элемента состояния. Отдельные элементы можно определить как элементы обратного вызова, которые полезны, если ваше приложение уже хранит некоторые сведения для элемента.  
  
 Можно определить элемент как элемент обратного вызова, указав соответствующие значения для `pszText` и `iImage` члены **LV_ITEM** структуры (см. [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Если приложение сохраняет текст элемента или подэлемента, укажите **LPSTR_TEXTCALLBACK** значение для `pszText` элемента. Если приложение хранит отслеживания о значок для элемента, укажите **I_IMAGECALLBACK** значение для `iImage` элемента.  
  
 Кроме определения элементы обратного вызова, можно также изменить маска обратного вызова элемента управления. Эта маска — это набор битовых флагов, указывающих состояния элементов, для которых приложение, а не элемент управления сохраняет текущие данные. Маска обратного вызова применяется ко всем элементам управления, в отличие от обозначение элемент обратного вызова, который относится к конкретному элементу. Маска обратного вызова по умолчанию равно нулю, это означает, что элемент управления отслеживает все состояния элемента. Чтобы изменить это поведение по умолчанию, инициализируйте битовой маске любое сочетание следующих значений:  
  
-   `LVIS_CUT`Элемент помечен для операции вырезания и вставки.  
  
-   `LVIS_DROPHILITED`Элемент выделяется в качестве целевого объекта и перетащите.  
  
-   `LVIS_FOCUSED`Элемент имеет фокус.  
  
-   `LVIS_SELECTED`Элемент выбран.  
  
-   **LVIS_OVERLAYMASK** приложение хранит список индекс изображения текущего изображения наложение для каждого элемента.  
  
-   **LVIS_STATEIMAGEMASK** приложение хранит список индекс изображения текущего изображения состояния для каждого элемента.  
  
 Сведения на получение и задание этой маски в разделе [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) и [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

