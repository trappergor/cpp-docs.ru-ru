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
ms.openlocfilehash: 4bbf7014fc1b612804289dcb647f85b5e7905aeb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244393"
---
# <a name="cd2drectu-class"></a>Класс CD2DRectU

Программа-оболочка для `D2D1_RECT_U`.

## <a name="syntax"></a>Синтаксис

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Перегружен. Создает `CD2DRectU` объекта из `D2D1_RECT_U` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|Возвращает **логическое** значение, указывающее, является ли выражение содержит недопустимые данные (NULL).|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CD2DRectU::operator CRect](#operator_crect)|Преобразует `CD2DRectU` для `CRect` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2drectu"></a>  CD2DRectU::CD2DRectU

Создает объект CD2DRectU из объекта CRect.

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
исходный прямоугольник

*uLeft*<br/>
Левая координата источника

*uTop*<br/>
Верхняя координата источника

*uRight*<br/>
Источник прямо координат

*uBottom*<br/>
Нижняя координата источника

##  <a name="isnull"></a>  CD2DRectU::ISNULL

Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если начало прямоугольника, левую, нижнюю и правильные значения равны 0; в противном случае — значение FALSE.

##  <a name="operator_crect"></a>  CD2DRectU::operator CRect

Преобразует CD2DRectU CRect.

```
operator CRect();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение прямоугольника D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
