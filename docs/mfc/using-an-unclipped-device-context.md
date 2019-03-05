---
title: Использование необрезанного контекста устройства
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 0f129c0bfa5bd76df4ba34b117e7ed8aa08c2ecb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270674"
---
# <a name="using-an-unclipped-device-context"></a>Использование необрезанного контекста устройства

Если имеется полная уверенность, элемент управления не рисовать за пределами его клиентской прямоугольной области, можно получить прирост скорости небольшую, но выявляемых при отключение вызова `IntersectClipRect` , сделанных `COleControl`. Чтобы сделать это, удалите *clipPaintDC* флаг из набора флагов, возвращенный [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

При выборе, автоматически создается код, чтобы удалить этот флаг **Необрезанного контекста устройства** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) странице, при создании элемента управления с помощью мастера элементов управления ActiveX MFC.

Если вы используете активации без окна, эта оптимизация не оказывает влияния.

## <a name="see-also"></a>См. также

[Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)
