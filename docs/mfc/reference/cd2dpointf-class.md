---
title: Класс CD2DPointF
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 5d66c31289f9e17df99df4681cff1d5cf6a0ec86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369157"
---
# <a name="cd2dpointf-class"></a>Класс CD2DPointF

Программа-оболочка для `D2D1_POINT_2F`.

## <a name="syntax"></a>Синтаксис

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPointF:CD2DPointF](#cd2dpointf)|Перегружен. Строит `CD2DPointF` объект из `D2D1_POINT_2F` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPointF:оператор CPoint](#operator_cpoint)|`CD2DPointF` Преобразуется `CPoint` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a>CD2DPointF:CD2DPointF

Строит объект CD2DPointF с объекта CPoint.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
источник точки

*Fx*<br/>
источник X

*Fy*<br/>
источник Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointF:оператор CPoint

Преобразует CD2DPointF в объект CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение точки D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
