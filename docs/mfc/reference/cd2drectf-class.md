---
title: Класс CD2DRectF
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 33d3c5f9e795ad6c91b689436e8a3b1b56966dce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369123"
---
# <a name="cd2drectf-class"></a>Класс CD2DRectF

Программа-оболочка для `D2D1_RECT_F`.

## <a name="syntax"></a>Синтаксис

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Перегружен. Строит `CD2DRectF` объект из `D2D1_RECT_F` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|Возвращает значение **boolean,** которое указывает, не содержит ли выражение действительных данных (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectF:оператор CRect](#operator_crect)|`CD2DRectF` Преобразуется `CRect` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2drectfcd2drectf"></a><a name="cd2drectf"></a>CD2DRectF::CD2DRectF

Строит объект CD2DRectF с объекта CRect.

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
источник прямоугольника

*fLeft*<br/>
источник левой координат

*fТоп*<br/>
источник верхней координаты

*Испуг*<br/>
источник правой координат

*fBottom*<br/>
источник нижней координаты

## <a name="cd2drectfisnull"></a><a name="isnull"></a>CD2DRectF::IsNull

Возвращает значение Boolean, которое указывает, не содержит ли выражение действительных данных (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если прямоугольник в верхней, левой, нижней и правой значения все равны 0; в противном случае FALSE.

## <a name="cd2drectfoperator-crect"></a><a name="operator_crect"></a>CD2DRectF:оператор CRect

Преобразует CD2DRectF в объект CRect.

```
operator CRect();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение прямоугольника D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
