---
title: Стили элемента управления хода выполнения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1044c82c2864d71047e4fe3c7461d03a17d9d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="styles-for-the-progress-control"></a>Стили для элемента управления "Индикатор выполнения"
При первоначальном создании управления хода выполнения ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create)), используйте `dwStyle` для указания стили необходимое окно для элемента управления хода выполнения. В следующем списке приводятся стили применимые окна. Элемент управления игнорирует любые стили окна, отличные от указанных здесь. Рекомендуется всегда создавать элемент управления как дочернего окна, обычно из родительского поля диалогового окна.  
  
|Стиль окна|Действие|  
|------------------|------------|  
|`WS_BORDER`|Создает обрамление вокруг окна.|  
|**WS_CHILD**|Создает дочернее окно (всегда должна использоваться для `CProgressCtrl`).|  
|**WS_CLIPCHILDREN**|Исключает область, занимаемую дочерних окон при рисовании в родительском окне. Используется при создании родительского окна.|  
|**WS_CLIPSIBLINGS**|Отсекает дочерних окон друг относительно друга.|  
|**WS_DISABLED**|Создает окно, которое изначально отключены.|  
|**WS_VISIBLE**|Создает окно, которое изначально является видимым.|  
|**WS_TABSTOP**|Указывает, что элемент управления может получать фокус, когда пользователь нажимает клавишу TAB, чтобы переместить в нее.|  
  
 Кроме того, можно указать два стиля, применяемые только к на соответствующем элементе управления `PBS_VERTICAL` и `PBS_SMOOTH`.  
  
 Используйте `PBS_VERTICAL` пользователям элемента управления по вертикали, а не по горизонтали. Используйте `PBS_SMOOTH` для заполнения элемента управления полностью, вместо вывода маленьких отделенным квадратов, добавочного заполнения элемента управления.  
  
 Без `PBS_SMOOTH` стиля:  
  
 ![Стандартный стиль индикатора выполнения](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 С `PBS_SMOOTH` и `PBS_VERTICAL` стили:  
  
 ![Индикатор выполнения стиля, гладкий и вертикальный](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 Дополнительные сведения см. в разделе [стили окна](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) в *Справочник по библиотеке MFC*.  
  
## <a name="see-also"></a>См. также  
 [Использование CProgressCtrl](../mfc/using-cprogressctrl.md)

