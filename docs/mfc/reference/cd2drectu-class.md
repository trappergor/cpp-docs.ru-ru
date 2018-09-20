---
title: Класс CD2DRectU | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd6a9bdc5539b2e6d4faf35c47b208ec0d83ea92
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444186"
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
|[CD2DRectU::CD2DRectU](#cd2drectu)|Перегружен. Создает `CD2DRectU` объекта из `D2D1_RECT_U` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DRectU::ISNULL](#isnull)|Возвращает **логическое** значение, указывающее, является ли выражение содержит недопустимые данные (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
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

*Rect*<br/>
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
