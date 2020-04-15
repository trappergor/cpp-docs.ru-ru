---
title: Класс CD2DSolidColorBrush
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: 5aa3d7688046b0c1b04983f2d27fe5579dd7c680
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369057"
---
# <a name="cd2dsolidcolorbrush-class"></a>Класс CD2DSolidColorBrush

Обертка для ID2D1SolidColorBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Перегружен. Строит объект CD2DSolidColorBrush.|
|[CD2DSolidColorBrush:: »CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|Деструктор Вызывается при уничтожении твердого объекта кисти D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DSolidColorBrush::Создание](#create)|Создает CD2DSolidColorBrush. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::Destroy](#destroy)|Уничтожает объект CD2DSolidColorBrush. (Отменяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DSolidColorBrush::Get](#get)|Возвращает интерфейс ID2D1SolidColorBrush|
|[CD2DSolidColorBrush::GetColor](#getcolor)|Получает цвет твердой цветовой кисти|
|[CD2DSolidColorBrush::SetColor](#setcolor)|Определяет цвет этой твердой цветовой кисти|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::оператор ID2D1SolidColorBrush](#operator_id2d1solidcolorbrush_star)|Возвращает интерфейс ID2D1SolidColorBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush:::m_colorSolid](#m_colorsolid)|Кисть твердого цвета.|
|[CD2DSolidColorBrush:::m_pSolidColorBrush](#m_psolidcolorbrush)|Хранит указатель на объект ID2D1SolidColorBrush.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2DSolidColorBrush:: »CD2DSolidColorBrush

Деструктор Вызывается при уничтожении твердого объекта кисти D2D.

```
virtual ~CD2DSolidColorBrush();
```

## <a name="cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2DSolidColorBrush::Attach

Прикрепляет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2DSolidColorBrush::CD2DSolidColorBrush

Строит объект CD2DSolidColorBrush.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*Цвет*<br/>
Красные, зеленые, синие и альфа-значения цвета кисти.

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

*nАльфа*<br/>
Непрозрачность цвета кисти.

## <a name="cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2DSolidColorBrush::Создание

Создает CD2DSolidColorBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2DSolidColorBrush::Destroy

Уничтожает объект CD2DSolidColorBrush.

```
virtual void Destroy();
```

## <a name="cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2DSolidColorBrush::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dsolidcolorbrushget"></a><a name="get"></a>CD2DSolidColorBrush::Get

Возвращает интерфейс ID2D1SolidColorBrush

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1SolidColorBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2DSolidColorBrush::GetColor

Получает цвет твердой цветовой кисти

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет этой твердой цветовой кисти

## <a name="cd2dsolidcolorbrushm_colorsolid"></a><a name="m_colorsolid"></a>CD2DSolidColorBrush:::m_colorSolid

Кисть твердого цвета.

```
D2D1_COLOR_F m_colorSolid;
```

## <a name="cd2dsolidcolorbrushm_psolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2DSolidColorBrush:::m_pSolidColorBrush

Хранит указатель на объект ID2D1SolidColorBrush.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

## <a name="cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2DSolidColorBrush::оператор ID2D1SolidColorBrush

Возвращает интерфейс ID2D1SolidColorBrush

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1SolidColorBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2DSolidColorBrush::SetColor

Определяет цвет этой твердой цветовой кисти

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Цвет этой твердой цветовой кисти

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
