---
title: Класс CD2DBitmapBrush | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b40f7e3d4a37dbc73494444fbfcc398621b7ec4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080017"
---
# <a name="cd2dbitmapbrush-class"></a>Класс CD2DBitmapBrush

Оболочка для ID2D1BitmapBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Перегружен. Создает объект CD2DBitmapBrush из файла.|
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Деструктор Вызывается при уничтожении объекта D2D кисть растрового изображения.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DBitmapBrush::CREATE](#create)|Создает CD2DBitmapBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::destroy](#destroy)|Уничтожает объект CD2DBitmapBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DBitmapBrush::Get](#get)|Возвращает интерфейс ID2D1BitmapBrush|
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Получает источник растрового изображения, эта кисть используется для рисования|
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Получает метод, по которому кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения|
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Получает метод, по которому кисть по вертикали плитки тех областей, которые выходить за его растрового изображения|
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Возвращает метод интерполяции, используемый при кисть растрового изображения является масштабировании или повороте|
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Указывает источник растрового изображения, эта кисть используется для рисования|
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Указывает, как кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения|
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Указывает, как кисть по вертикали плитки тех областей, которые выходить за его растрового изображения|
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Указывает режим интерполяции, используемый при кисть растрового изображения является масштабировании или повороте|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::CommonInit](#commoninit)|Инициализирует объект|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Возвращает интерфейс ID2D1BitmapBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|Содержит указатель на объект CD2DBitmap.|
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|Содержит указатель на объект ID2D1BitmapBrush.|
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Свойства кисти для точечных рисунков.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="dtor"></a>  CD2DBitmapBrush:: ~ CD2DBitmapBrush

Деструктор Вызывается при уничтожении объекта D2D кисть растрового изображения.

```
virtual ~CD2DBitmapBrush();
```

##  <a name="attach"></a>  CD2DBitmapBrush::Attach

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dbitmapbrush"></a>  CD2DBitmapBrush::CD2DBitmapBrush

Создает объект CD2DBitmapBrush.

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*pBitmapBrushProperties*<br/>
Указатель на режимы расширить и режим интерполяции кисть растрового изображения.

*pBrushProperties*<br/>
Указатель на непрозрачность и преобразования кисти.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

*uiResID*<br/>
Идентификатор ресурса ресурса.

*lpszType*<br/>
Указатель на заканчивающуюся нулем строку, содержащую тип ресурса.

*sizeDest*<br/>
Целевой размер растрового изображения.

*lpszImagePath*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя файла.

##  <a name="commoninit"></a>  CD2DBitmapBrush::CommonInit

Инициализирует объект

```
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>Параметры

*pBitmapBrushProperties*<br/>
Указатель на свойства кисть растрового изображения.

##  <a name="create"></a>  CD2DBitmapBrush::CREATE

Создает CD2DBitmapBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на целевой объект отрисовки.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DBitmapBrush::destroy

Уничтожает объект CD2DBitmapBrush.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBitmapBrush::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="get"></a>  CD2DBitmapBrush::Get

Возвращает интерфейс ID2D1BitmapBrush

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.

##  <a name="getbitmap"></a>  CD2DBitmapBrush::GetBitmap

Получает источник растрового изображения, эта кисть используется для рисования

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект CD2DBitmap или значение NULL, если объект еще не инициализирован.

##  <a name="getextendmodex"></a>  CD2DBitmapBrush::GetExtendModeX

Получает метод, по которому кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения

##  <a name="getextendmodey"></a>  CD2DBitmapBrush::GetExtendModeY

Получает метод, по которому кисть по вертикали плитки тех областей, которые выходить за его растрового изображения

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходить за его растрового изображения

##  <a name="getinterpolationmode"></a>  CD2DBitmapBrush::GetInterpolationMode

Возвращает метод интерполяции, используемый при кисть растрового изображения является масштабировании или повороте

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод интерполяции, используемый при кисть растрового изображения является масштабировании или повороте

##  <a name="m_pbitmap"></a>  CD2DBitmapBrush::m_pBitmap

Содержит указатель на объект CD2DBitmap.

```
CD2DBitmap* m_pBitmap;
```

##  <a name="m_pbitmapbrush"></a>  CD2DBitmapBrush::m_pBitmapBrush

Содержит указатель на объект ID2D1BitmapBrush.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

##  <a name="m_pbitmapbrushproperties"></a>  CD2DBitmapBrush::m_pBitmapBrushProperties

Свойства кисти для точечных рисунков.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

##  <a name="operator_id2d1bitmapbrush_star"></a>  CD2DBitmapBrush::operator ID2D1BitmapBrush *

Возвращает интерфейс ID2D1BitmapBrush

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.

##  <a name="setbitmap"></a>  CD2DBitmapBrush::SetBitmap

Указывает источник растрового изображения, эта кисть используется для рисования

```
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Источник растрового изображения, используемые кисти

##  <a name="setextendmodex"></a>  CD2DBitmapBrush::SetExtendModeX

Указывает, как кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения

```
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>Параметры

*extendModeX*<br/>
Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходить за его растрового изображения

##  <a name="setextendmodey"></a>  CD2DBitmapBrush::SetExtendModeY

Указывает, как кисть по вертикали плитки тех областей, которые выходить за его растрового изображения

```
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>Параметры

*extendModeY*<br/>
Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходить за его растрового изображения

##  <a name="setinterpolationmode"></a>  CD2DBitmapBrush::SetInterpolationMode

Указывает режим интерполяции, используемый при кисть растрового изображения является масштабировании или повороте

```
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>Параметры

*interpolationMode*<br/>
Режим интерполяции, используемый для точечного рисунка кисти масштабируется или (повернутый)

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
