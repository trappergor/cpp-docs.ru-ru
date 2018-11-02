---
title: Структура POINT
ms.date: 10/12/2018
f1_keywords:
- POINT
- LPPOINT
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
ms.openlocfilehash: c53f250b714c66e74a12432b879cbc4bcc1fd88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646905"
---
# <a name="point-structure"></a>Структура POINT

`POINT` Структура определяет x*-* и координаты y точки.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagPOINT {
    LONG x;
    LONG y;
} POINT;
```

#### <a name="parameters"></a>Параметры

*x*<br/>
Задает координату по оси x точки.

*y*<br/>
Задает координату по оси y точки.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** windef.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)
