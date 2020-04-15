---
title: Класс CD2DRectU
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: 26e647ae01a498a6ad8ca2d7c866f33b01910881
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369112"
---
# <a name="cd2drectu-class"></a>Класс CD2DRectU

Программа-оболочка для `D2D1_RECT_U`.

## <a name="syntax"></a>Синтаксис

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Перегружен. Строит `CD2DRectU` объект из `D2D1_RECT_U` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|Возвращает значение **boolean,** которое указывает, не содержит ли выражение действительных данных (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectU:оператор CRect](#operator_crect)|`CD2DRectU` Преобразуется `CRect` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU

Строит объект CD2DRectU с объекта CRect.

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
источник прямоугольника

*uLeft*<br/>
источник левой координат

*uTop*<br/>
источник верхней координаты

*uПраво*<br/>
источник правой координат

*uBottom*<br/>
источник нижней координаты

## <a name="cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull

Возвращает значение Boolean, которое указывает, не содержит ли выражение действительных данных (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если прямоугольник в верхней, левой, нижней и правой значения все равны 0; в противном случае FALSE.

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU:оператор CRect

Преобразует CD2DRectU в объект CRect.

```
operator CRect();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение прямоугольника D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
