---
title: Оптимизация рисования элементов управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8103e1e342756f9b715c1a0959ed256403e130bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351298"
---
# <a name="optimizing-control-drawing"></a>Оптимизация рисования элементов управления
Если элемент управления является нарисовать сам себя в контексте устройства указан контейнер, он обычно выбирает объекты GDI (например, перья, кисти и шрифты) в контексте устройства, выполняет операции рисования и восстанавливает предыдущие объекты GDI. Если контейнер содержит несколько элементов управления, которые должны отображаться в один и тот же контекст устройства, а каждый элемент управления выбирает необходимые объекты GDI, времени могут быть сохранены, если элементы управления не следует восстанавливать по отдельности ранее выбранные объекты. После отображения всех элементов управления контейнера можно автоматически восстановить исходные объекты.  
  
 Для определения того, поддерживает ли эта методика контейнер, можно вызвать элемент управления [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) функции-члена. Если эта функция возвращает **TRUE**, элемент управления можно пропустить для обычного восстановления ранее выбранные объекты.  
  
 Элемент управления, имеющий следующее (неоптимизированные) рассмотрите возможность `OnDraw` функции:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]  
  
 Перо и кисть в этом примере являются локальные переменные, то есть деструкторы, будет вызываться, когда они выходят за пределы области действия (при `OnDraw` функции заканчивается). Деструкторы попытается удалить соответствующие объекты GDI. Но они не должны удаляться при планировании оставить их выделенных в контексте устройства при возвращении с `OnDraw`.  
  
 Чтобы предотвратить [CPen](../mfc/reference/cpen-class.md) и [CBrush](../mfc/reference/cbrush-class.md) объектов из при уничтожении `OnDraw` завершит, сохранять их в переменных-членов вместо локальных переменных. В объявлении класса элемента управления добавьте объявления для две новые переменные-члены:  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]  
  
 Затем `OnDraw` функции можно переписать следующим образом:  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]  
  
 Такой подход позволяет избежать создания перо и кисть каждый раз `OnDraw` вызывается. Улучшения быстродействия наносит ущерб поддержку дополнительного экземпляра данных.  
  
 При изменении свойства ForeColor или BackColor, пера или кисти необходимо создать заново. Чтобы сделать это, переопределите [OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) и [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) функции-члены:  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]  
  
 Наконец Чтобы удалить ненужные `SelectObject` вызовы, изменение `OnDraw` следующим образом:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Элементы управления MFC ActiveX: оптимизация](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl-класс](../mfc/reference/colecontrol-class.md)   
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md)   
 [Элементы ActiveX в MFC. Закраска элементов ActiveX](../mfc/mfc-activex-controls-painting-an-activex-control.md)

