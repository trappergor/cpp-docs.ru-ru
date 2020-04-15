---
title: Класс CD2DEllipse
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 82ad2fbfb8558486134f85d7ec9bcaa6eb4e7507
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369261"
---
# <a name="cd2dellipse-class"></a>Класс CD2DEllipse

Программа-оболочка для `D2D1_ELLIPSE`.

## <a name="syntax"></a>Синтаксис

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Перегружен. Строит `CD2DEllipse` объект из `D2D1_ELLIPSE` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse

Строит объект CD2DEllipse с объекта CD2DRectF.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
источник прямоугольника

*ellipse*<br/>
источник эллипса

*ptCenter*<br/>
Центральная точка эллипса.

*размерРадиус*<br/>
X-радиус и Y-радиус эллипса.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
