---
title: Класс CD2DPointU
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 8c6db55f1dde1fd054a1f75590f5969c097b2f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369146"
---
# <a name="cd2dpointu-class"></a>Класс CD2DPointU

Программа-оболочка для `D2D1_POINT_2U`.

## <a name="syntax"></a>Синтаксис

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPointU:CD2DPointU](#cd2dpointu)|Перегружен. Строит `CD2DPointU` из объекта. `D2D1_POINT_2U`|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPointU:оператор CPoint](#operator_cpoint)|`CD2DPointU` Преобразуется `CPoint` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dpointucd2dpointu"></a><a name="cd2dpointu"></a>CD2DPointU:CD2DPointU

Строит объект CD2DPointU с объекта CPoint.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
источник точки

*Ux*<br/>
источник X

*Uy*<br/>
источник Y

## <a name="cd2dpointuoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointU:оператор CPoint

Преобразует CD2DPointU в объект CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение точки D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
