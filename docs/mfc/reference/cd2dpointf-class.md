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
ms.openlocfilehash: b8fe808c3147fa52c5041e2988822ace0ba60896
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304045"
---
# <a name="cd2dpointf-class"></a>Класс CD2DPointF

Программа-оболочка для `D2D1_POINT_2F`.

## <a name="syntax"></a>Синтаксис

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Перегружен. Создает `CD2DPointF` объекта из `D2D1_POINT_2F` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPointF::operator CPoint](#operator_cpoint)|Преобразует `CD2DPointF` для `CPoint` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2dpointf"></a>  CD2DPointF::CD2DPointF

Создает объект CD2DPointF из CPoint объекта.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Исходная точка

*fX*<br/>
Источник X

*fY*<br/>
Источник Y

##  <a name="operator_cpoint"></a>  CD2DPointF::operator CPoint

Преобразует CD2DPointF CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение точки D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
