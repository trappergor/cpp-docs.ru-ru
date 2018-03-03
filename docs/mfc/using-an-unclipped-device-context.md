---
title: "Использование Необрезанного контекста устройства | Документы Microsoft"
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
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae095b59b07132bd7e4c6892b8e58d9e69fb39c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

