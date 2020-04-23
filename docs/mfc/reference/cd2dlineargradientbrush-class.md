---
title: Класс CD2DLinearGradientBrush
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: d87cdae5c24eae391be8db2fcdd04f91d592e427
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753155"
---
# <a name="cd2dlineargradientbrush-class"></a>Класс CD2DLinearGradientBrush

Обертка для ID2D1LinearGradientBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Строит объект CD2DLinearGradientBrush.|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Деструктор Вызывается при уничтожении объекта линейной градиентной кисти D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DLinearGradientBrush::Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DLinearGradientBrush::Создание](#create)|Создает CD2DLinearGradientBrush. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::Destroy](#destroy)|Уничтожает объект CD2DLinearGradientBrush. (Отменяет [CD2DGradientBrush: :Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DLinearGradientBrush::Get](#get)|Возвращает интерфейс ID2D1LinearGradientBrush|
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Извлекает окончание координат линейного градиента|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Извлекает начальные координаты линейного градиента|
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Устанавливает конечную координату линейного градиента в пространстве координат кисти|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Устанавливает начальные координаты линейного градиента в пространстве координат кисти|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLinearGradientBrush:Оператор ID2D1LinearGradientBrush](#operator_id2d1lineargradientbrush_star)|Возвращает интерфейс ID2D1LinearGradientBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Точки начала и конца градиента.|
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Указатель на ID2D1LinearGradientBrush.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush

Деструктор Вызывается при уничтожении объекта линейной градиентной кисти D2D.

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2DLinearGradientBrush::Attach

Прикрепляет существующий интерфейс ресурса к объекту

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush

Строит объект CD2DLinearGradientBrush.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
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

*ЛинейныйГрадиентБруриентСвойства*<br/>
Точки начала и конца градиента.

*цветИнтерполацииГамма*<br/>
Пространство, в котором выполняется цветовая интерполяция между остановками градиента.

*extendMode*<br/>
Поведение градиента за пределами диапазона «0,1».

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2DLinearGradientBrush::Создание

Создает CD2DLinearGradientBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2DLinearGradientBrush::Destroy

Уничтожает объект CD2DLinearGradientBrush.

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2DLinearGradientBrush::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a>CD2DLinearGradientBrush::Get

Возвращает интерфейс ID2D1LinearGradientBrush

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1LinearGradientBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2DLinearGradientBrush::GetEndPoint

Извлекает окончание координат линейного градиента

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Возвращаемое значение

Окончание двухмерных координат линейного градиента в пространстве координат кисти

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint

Извлекает начальные координаты линейного градиента

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Возвращаемое значение

Стартовые двухмерные координаты линейного градиента в пространстве координат кисти

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2DLinearGradientBrush::m_LinearGradientBrushProperties

Точки начала и конца градиента.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2DLinearGradientBrush::m_pLinearGradientBrush

Указатель на ID2D1LinearGradientBrush.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradientBrush:Оператор ID2D1LinearGradientBrush

Возвращает интерфейс ID2D1LinearGradientBrush

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1LinearGradientBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2DLinearGradientBrush::SetEndPoint

Устанавливает конечную координату линейного градиента в пространстве координат кисти

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Окончание двухмерных координат линейного градиента в пространстве координат кисти

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint

Устанавливает начальные координаты линейного градиента в пространстве координат кисти

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Стартовые двухмерные координаты линейного градиента в пространстве координат кисти

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
