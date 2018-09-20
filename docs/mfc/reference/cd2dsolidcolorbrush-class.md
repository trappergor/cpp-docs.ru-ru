---
title: Класс CD2DSolidColorBrush | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb261fde28755d69e68ee7cf3bf69031ace69893
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437760"
---
# <a name="cd2dsolidcolorbrush-class"></a>Класс CD2DSolidColorBrush

Оболочка для ID2D1SolidColorBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Перегружен. Создает объект CD2DSolidColorBrush.|
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|Деструктор Вызывается при уничтожении объекта D2D сплошную кисть.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DSolidColorBrush::CREATE](#create)|Создает CD2DSolidColorBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::destroy](#destroy)|Уничтожает объект CD2DSolidColorBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DSolidColorBrush::Get](#get)|Возвращает интерфейс ID2D1SolidColorBrush|
|[CD2DSolidColorBrush::GetColor](#getcolor)|Получает цвет Одноцветная кисть|
|[CD2DSolidColorBrush::SetColor](#setcolor)|Указывает цвет этой кисти сплошным цветом|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|Возвращает интерфейс ID2D1SolidColorBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|Одноцветная кисть.|
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|Содержит указатель на объект ID2D1SolidColorBrush.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="_dtorcd2dsolidcolorbrush"></a>  CD2DSolidColorBrush:: ~ CD2DSolidColorBrush

Деструктор Вызывается при уничтожении объекта D2D сплошную кисть.

```
virtual ~CD2DSolidColorBrush();
```

##  <a name="attach"></a>  CD2DSolidColorBrush::Attach

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::CD2DSolidColorBrush

Создает объект CD2DSolidColorBrush.

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
Указатель на целевой объект отрисовки.

*Цвет*<br/>
Значения красного, зеленого, синего и альфа-цвета кисти.

*pBrushProperties*<br/>
Указатель на непрозрачность и преобразования кисти.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

*nAlpha*<br/>
Прозрачность цвет кисти.

##  <a name="create"></a>  CD2DSolidColorBrush::CREATE

Создает CD2DSolidColorBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на целевой объект отрисовки.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DSolidColorBrush::destroy

Уничтожает объект CD2DSolidColorBrush.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DSolidColorBrush::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="get"></a>  CD2DSolidColorBrush::Get

Возвращает интерфейс ID2D1SolidColorBrush

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1SolidColorBrush или значение NULL, если объект еще не инициализирован.

##  <a name="getcolor"></a>  CD2DSolidColorBrush::GetColor

Получает цвет Одноцветная кисть

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет этой кисти сплошным цветом

##  <a name="m_colorsolid"></a>  CD2DSolidColorBrush::m_colorSolid

Одноцветная кисть.

```
D2D1_COLOR_F m_colorSolid;
```

##  <a name="m_psolidcolorbrush"></a>  CD2DSolidColorBrush::m_pSolidColorBrush

Содержит указатель на объект ID2D1SolidColorBrush.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

##  <a name="operator_id2d1solidcolorbrush_star"></a>  CD2DSolidColorBrush::operator ID2D1SolidColorBrush *

Возвращает интерфейс ID2D1SolidColorBrush

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1SolidColorBrush или значение NULL, если объект еще не инициализирован.

##  <a name="setcolor"></a>  CD2DSolidColorBrush::SetColor

Указывает цвет этой кисти сплошным цветом

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Цвет этой кисти сплошным цветом

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
