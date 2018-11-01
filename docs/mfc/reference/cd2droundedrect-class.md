---
title: Класс CD2DRoundedRect
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 6c1aa2bb9593cdf12aadc39ef8a85cc8ad14078a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677478"
---
# <a name="cd2droundedrect-class"></a>Класс CD2DRoundedRect

Программа-оболочка для `D2D1_ROUNDED_RECT`.

## <a name="syntax"></a>Синтаксис

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Перегружен. Создает `CD2DRoundedRect` объекта из `D2D1_ROUNDED_RECT` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2droundedrect"></a>  CD2DRoundedRect::CD2DRoundedRect

Создает объект CD2DRoundedRect из CD2DRectF объект.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Параметры

*rectIn*<br/>
исходный прямоугольник

*sizeRadius*<br/>
размер RADIUS

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
