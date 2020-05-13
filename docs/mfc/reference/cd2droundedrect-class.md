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
ms.openlocfilehash: 5189f3d824c008845570eac6eead4a35be1e483d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369075"
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
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Перегружен. Строит `CD2DRoundedRect` объект из `D2D1_ROUNDED_RECT` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a>CD2DRoundedRect::CD2DRoundedRect

Строит объект CD2DRoundedRect с объекта CD2DRectF.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Параметры

*rectIn*<br/>
источник прямоугольника

*размерРадиус*<br/>
размер радиуса

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
