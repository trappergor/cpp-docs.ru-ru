---
title: Класс CD2DRadialGradientBrush
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: aca9606271040e5c5c9aee81be0a08b64cf2bab7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369133"
---
# <a name="cd2dradialgradientbrush-class"></a>Класс CD2DRadialGradientBrush

Обертка для ID2D1RadialGradientBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Строит объект CD2DLinearGradientBrush.|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Деструктор Вызывается при уничтожении радиального градиента объекта D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DRadialGradientBrush::Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DRadialGradientBrush::Создание](#create)|Создает CD2DRadialGradientBrush. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DRadialGradientBrush::Destroy](#destroy)|Уничтожает объект CD2DRadialGradientBrush. (Отменяет [CD2DGradientBrush: :Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DRadialGradientBrush::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DRadialGradientBrush::Get](#get)|Возвращает интерфейс ID2D1RadialGradientBrush|
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Извлекает центр градиента эллипса|
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Извлекает смещение градиентного происхождения по отношению к центру градиента эллипса|
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Извлекает x-радиус градиентного эллипса|
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Извлекает y-радиус градиентного эллипса|
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Определяет центр эллипса градиента в пространстве координат кисти|
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Определяет смещение градиентного происхождения относительно центра градиента эллипса|
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Определяет x-радиус эллипса градиента в пространстве координат кисти|
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Определяет y-радиус градиентного эллипса в пространстве координат кисти|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DRadialGradientBrush::оператор ID2D1РадиалГрадиентБрур](#operator_id2d1radialgradientbrush_star)|Возвращает интерфейс ID2D1RadialGradientBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Указатель на ID2D1RadialGradientBrush.|
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Центр, градиентное смещение происхождения, и X-радиус и y-радиус градиента кисти.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush

Деструктор Вызывается при уничтожении радиального градиента объекта D2D.

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2DRadialGradientBrush::Attach

Прикрепляет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush

Строит объект CD2DLinearGradientBrush.

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
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

*РадиалГрадиентБруриенсперты*<br/>
Центр, градиентное смещение происхождения, и X-радиус и y-радиус градиента кисти.

*цветИнтерполацииГамма*<br/>
Пространство, в котором выполняется цветовая интерполяция между остановками градиента.

*extendMode*<br/>
Поведение градиента за пределами диапазона «0,1».

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2DRadialGradientBrush::Создание

Создает CD2DRadialGradientBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2DRadialGradientBrush::Destroy

Уничтожает объект CD2DRadialGradientBrush.

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2DRadialGradientBrush::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a>CD2DRadialGradientBrush::Get

Возвращает интерфейс ID2D1RadialGradientBrush

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1RadialGradientBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter

Извлекает центр градиента эллипса

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Возвращаемое значение

Центр градиентного эллипса. Это значение выражается в пространстве координат кисти

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset

Извлекает смещение градиентного происхождения по отношению к центру градиента эллипса

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Возвращаемое значение

Смещение градиентного происхождения из центра градиентного эллипса. Это значение выражается в пространстве координат кисти

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX

Извлекает x-радиус градиентного эллипса

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Возвращаемое значение

X-радиус градиентного эллипса. Это значение выражается в пространстве координат кисти

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY

Извлекает y-радиус градиентного эллипса

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Y-радиус градиентного эллипса. Это значение выражается в пространстве координат кисти

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush

Указатель на ID2D1RadialGradientBrush.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties

Центр, градиентное смещение происхождения, и X-радиус и y-радиус градиента кисти.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::оператор ID2D1РадиалГрадиентБрур

Возвращает интерфейс ID2D1RadialGradientBrush

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1RadialGradientBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter

Определяет центр эллипса градиента в пространстве координат кисти

```
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Центр эллипса градиента, в пространстве координат кисти

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset

Определяет смещение градиентного происхождения относительно центра градиента эллипса

```
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>Параметры

*gradientOriginOffset*<br/>
Смещение градиентного происхождения из центра градиентного эллипса

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX

Определяет x-радиус эллипса градиента в пространстве координат кисти

```
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>Параметры

*radiusX*<br/>
X-радиус градиентного эллипса. Это значение находится в пространстве координат кисти

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY

Определяет y-радиус градиентного эллипса в пространстве координат кисти

```
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>Параметры

*радиусY*<br/>
Y-радиус градиентного эллипса. Это значение находится в пространстве координат кисти

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
