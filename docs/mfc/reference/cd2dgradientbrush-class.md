---
title: Класс CD2DGradientBrush
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: 861bc32382737bd6482a3d51eb8470bf834e8508
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369218"
---
# <a name="cd2dgradientbrush-class"></a>Класс CD2DGradientBrush

Базовый класс классов CD2DLinearGradientBrush и CD2DRadialGradientBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Строит объект CD2DGradientBrush.|
|[CD2DGradientBrush:: »CD2DGradientBrush](#_dtorcd2dgradientbrush)|Деструктор Вызывается при уничтожении объекта градиентной кисти D2D.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DGradientBrush::Destroy](#destroy)|Уничтожает объект CD2DGradientBrush. (Отменяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|Массив D2D1_GRADIENT_STOP структур.|
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Пространство, в котором выполняется цветовая интерполяция между остановками градиента.|
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|Поведение градиента за пределами диапазона «0,1».|
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Указатель на массив D2D1_GRADIENT_STOP структур.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2DGradientBrush:: »CD2DGradientBrush

Деструктор Вызывается при уничтожении объекта градиентной кисти D2D.

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2DGradientBrush::CD2DGradientBrush

Строит объект CD2DGradientBrush.

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*gradientStops*<br/>
Указатель на массив D2D1_GRADIENT_STOP структур.

*градиентСтопсктом*<br/>
Значение, превышающее или равное 1, которое определяет количество остановок градиента в массиве gradientStops.

*цветИнтерполацииГамма*<br/>
Пространство, в котором выполняется цветовая интерполяция между остановками градиента.

*extendMode*<br/>
Поведение градиента за пределами диапазона «0,1».

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2DGradientBrush::Destroy

Уничтожает объект CD2DGradientBrush.

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a>CD2DGradientBrush::m_arGradientStops

Массив D2D1_GRADIENT_STOP структур.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2DGradientBrush::m_colorInterpolationGamma

Пространство, в котором выполняется цветовая интерполяция между остановками градиента.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a>CD2DGradientBrush::m_extendMode

Поведение градиента за пределами диапазона «0,1».

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a>CD2DGradientBrush::m_pGradientStops

Указатель на массив D2D1_GRADIENT_STOP структур.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
