---
title: Структура MINMAXINFO
ms.date: 11/04/2016
f1_keywords:
- MINMAXINFO
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
ms.openlocfilehash: 11f55b1756623626769e21c006543b6993607b08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517849"
---
# <a name="minmaxinfo-structure"></a>Структура MINMAXINFO

`MINMAXINFO` Структура содержит сведения о размер развернутого окна и его отслеживания минимального и максимального размера и положения.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagMINMAXINFO {
    POINT ptReserved;
    POINT ptMaxSize;
    POINT ptMaxPosition;
    POINT ptMinTrackSize;
    POINT ptMaxTrackSize;
} MINMAXINFO;
```

#### <a name="parameters"></a>Параметры

*ptReserved*<br/>
Зарезервировано для внутреннего использования.

*ptMaxSize*<br/>
Указывает ширину развернутого (point.x) и высоту развернутого (point.y) окна.

*ptMaxPosition*<br/>
Указывает положение левой части развернутого окна (point.x) и положение верхней части развернутого окна (point.y).

*ptMinTrackSize*<br/>
Указывает минимальную отслеживаемую ширину (point.x) и Минимальная отслеживаемая высота окна (point.y).

*ptMaxTrackSize*<br/>
Указывает максимально отслеживаемая ширина (point.x) и максимально отслеживаемую высоту окна (point.y).

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

