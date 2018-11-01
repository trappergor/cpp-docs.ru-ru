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
ms.openlocfilehash: fad906510a111a2132d590d7c221d2484645f044
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591208"
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
|[CD2DRectF::CD2DRectF](#cd2drectf)|Перегружен. Создает `CD2DRectF` объекта из `D2D1_RECT_F` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectF::ISNULL](#isnull)|Возвращает **логическое** значение, указывающее, является ли выражение содержит недопустимые данные (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectF::operator CRect](#operator_crect)|Преобразует `CD2DRectF` для `CRect` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF

Создает CD2DRectF объект из объекта CRect.

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

*Rect*<br/>
исходный прямоугольник

*fLeft*<br/>
Левая координата источника

*fTop*<br/>
Верхняя координата источника

*fRight*<br/>
Источник прямо координат

*fBottom*<br/>
Нижняя координата источника

##  <a name="isnull"></a>  CD2DRectF::ISNULL

Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если начало прямоугольника, левую, нижнюю и правильные значения равны 0; в противном случае — значение FALSE.

##  <a name="operator_crect"></a>  CD2DRectF::operator CRect

Преобразует CD2DRectF объект CRect.

```
operator CRect();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение прямоугольника D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
