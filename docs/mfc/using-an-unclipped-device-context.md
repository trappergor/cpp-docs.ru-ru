---
title: Использование Необрезанного контекста устройства | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c76dc44993615e17ea3d99f9ac018a748e24d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-unclipped-device-context"></a>Использование необрезанного контекста устройства
Если имеется полная уверенность, элемент управления не рисовать за пределами его клиентской прямоугольной области, можно значительно прирост скорости небольшой, но обнаруживаются, отключив вызов `IntersectClipRect` , внесенных `COleControl`. Чтобы сделать это, удалите **clipPaintDC** флаг с набором флагов, возвращенных [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 При выборе автоматически создается код, чтобы удалить этот флаг **Необрезанного контекста устройства** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы, при создании элемента управления с помощью мастера элементов управления ActiveX MFC.  
  
 При использовании активации без окна Данная оптимизация не оказывает влияния.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

