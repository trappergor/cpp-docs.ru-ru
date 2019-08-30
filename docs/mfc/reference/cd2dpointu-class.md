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
ms.openlocfilehash: 6289d33aa0672d1ee423d91b11527dccfc868da7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177181"
---
# <a name="cd2dpointu-class"></a>Класс CD2DPointU

Программа-оболочка для `D2D1_POINT_2U`.

## <a name="syntax"></a>Синтаксис

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Перегружен. `CD2DPointU` Конструирует объект`D2D1_POINT_2U` из объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CD2DPointU:: operator CPoint](#operator_cpoint)|Преобразует `CD2DPointU` в`CPoint` объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Требования

**Заголовок:** афксрендертаржет. h

##  <a name="cd2dpointu"></a>CD2DPointU::CD2DPointU

Конструирует объект CD2DPointU из объекта CPoint.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Исходная точка

*Взаимодействия*<br/>
Источник X

*uY*<br/>
Источник Y

##  <a name="operator_cpoint"></a>CD2DPointU:: operator CPoint

Преобразует CD2DPointU в объект CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение точки D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
