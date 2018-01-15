---
title: "Эластичные соединения и средства отслеживания | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3bd9da00d2d6ea0110562f523a0adc53c1a476c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rubber-banding-and-trackers"></a>Эластичные соединения и средства отслеживания
Другой функцией, поставляемых вместе с средства отслеживания является выбор «изменяемый», который позволяет пользователю выбирать несколько элементов OLE, перетащив прямоугольник изменения размера вокруг выбираемых элементов. Когда пользователь отпускает левую кнопку мыши, элементы в пределах области, выбранных пользователем выбраны и доступными для пользователя. Например пользователь может перетащите его в другое приложение контейнера.  
  
 Для реализации этой функции требуется дополнительный код в вашем приложении `WM_LBUTTONDOWN` функция-обработчик.  
  
 В следующем образце кода реализует эластичное Выбор и дополнительные функции.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 Если вы хотите разрешить обратимое ориентации инспектор во время эластичные соединения, необходимо вызвать [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) с указанием третьего параметра равным **TRUE**. Помните, позволяя обратимое ориентации приведет иногда [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) чтобы стать инвертированный. Это можно исправить путем вызова [CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).  
  
 Дополнительные сведения см. в разделе [элементы клиента контейнера](../mfc/containers-client-items.md) и [Настройка перетаскивание](../mfc/drag-and-drop-customizing.md).  
  
## <a name="see-also"></a>См. также  
 [Средства отслеживания: Реализация средства отслеживания в приложении OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [Класс CRectTracker](../mfc/reference/crecttracker-class.md)
