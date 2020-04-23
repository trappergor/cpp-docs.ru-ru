---
title: Класс CD2DBitmapBrush
ms.date: 11/04/2016
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
ms.openlocfilehash: 8d0804c094204bc0e8ab420e20c8b6a6a35dc70a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754289"
---
# <a name="cd2dbitmapbrush-class"></a>Класс CD2DBitmapBrush

Обертка для ID2D1BitmapBrush.

## <a name="syntax"></a>Синтаксис

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Перегружен. Строит объект CD2DBitmapBrush из файла.|
|[CD2DBitmapBrush:: »CD2DBitmapBrush](#dtor)|Деструктор Вызывается при уничтожении объекта кисти Биткарты D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DBitmapBrush::Создание](#create)|Создает CD2DBitmapBrush. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::Destroy](#destroy)|Уничтожает объект CD2DBitmapBrush. (Отменяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DBitmapBrush::Get](#get)|Возвращает интерфейс ID2D1BitmapBrush|
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Получает источник биткарты, который эта кисть использует для рисования|
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Получает метод, с помощью которого кисть горизонтально плитки тех областях, которые расширяются мимо его bitmap|
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Получает метод, с помощью которого кисть вертикально плитки тех областях, которые простираются мимо его bitmap|
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Получает метод интерполяции, используемый при масштабировании или повороте кисти|
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Определяет источник биткарты, который эта кисть использует для краски|
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Определяет, как кисть горизонтально плитки тех областях, которые расширяются мимо его bitmap|
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Определяет, как кисть вертикально плитки тех областях, которые расширяются мимо его bitmap|
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Определяет режим интерполяции, используемый при масштабировании или повороте кисти|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapbrush::CommonInit](#commoninit)|Инициализация объекта|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::оператор ID2D1BitmapBrush](#operator_id2d1bitmapbrush_star)|Возвращает интерфейс ID2D1BitmapBrush|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|Хранит указатель на объект CD2DBitmap.|
|[CD2DBitmapBrush:::m_pBitmapBrush](#m_pbitmapbrush)|Хранит указатель на объект ID2D1BitmapBrush.|
|[CD2DBitmapBrush:::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Свойства кисти Bitmap.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2DBitmapBrush:: »CD2DBitmapBrush

Деструктор Вызывается при уничтожении объекта кисти Биткарты D2D.

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a>CD2DBitmapBrush::Attach

Прикрепляет существующий интерфейс ресурса к объекту

```cpp
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush

Строит объект CD2DBitmapBrush.

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
Указатель на цель рендера.

*pBitmapBrushСвойства*<br/>
Указатель на режимы расширения и режим интерполяции кисти bitmap.

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

*uiResID*<br/>
Идентификационный номер ресурса.

*lpszType*<br/>
Указатель на нулевую строку, содержащую тип ресурса.

*размерDest*<br/>
Размер назначения битной карты.

*lpszImagePath*<br/>
Указатель на нулевую строку, содержащую имя файла.

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2DBitmapbrush::CommonInit

Инициализация объекта

```cpp
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>Параметры

*pBitmapBrushСвойства*<br/>
Указатель на свойства кисти bitmap.

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a>CD2DBitmapBrush::Создание

Создает CD2DBitmapBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2DBitmapBrush::Destroy

Уничтожает объект CD2DBitmapBrush.

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2DBitmapBrush::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dbitmapbrushget"></a><a name="get"></a>CD2DBitmapBrush::Get

Возвращает интерфейс ID2D1BitmapBrush

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap

Получает источник биткарты, который эта кисть использует для рисования

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект CD2DBitmap или NULL, если объект еще не инициализирован.

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX

Получает метод, с помощью которого кисть горизонтально плитки тех областях, которые расширяются мимо его bitmap

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое определяет, как кисть горизонтально плитки тех областях, которые простираются мимо его bitmap

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY

Получает метод, с помощью которого кисть вертикально плитки тех областях, которые простираются мимо его bitmap

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое определяет, как кисть вертикально плитки тех областях, которые простираются мимо его bitmap

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode

Получает метод интерполяции, используемый при масштабировании или повороте кисти

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод интерполяции, используемый при масштабировании или повороте кисти

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap

Хранит указатель на объект CD2DBitmap.

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2DBitmapBrush:::m_pBitmapBrush

Хранит указатель на объект ID2D1BitmapBrush.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush:::m_pBitmapBrushProperties

Свойства кисти Bitmap.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::оператор ID2D1BitmapBrush

Возвращает интерфейс ID2D1BitmapBrush

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapBrush или NULL, если объект еще не инициализирован.

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap

Определяет источник биткарты, который эта кисть использует для краски

```cpp
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Источник биткарты, используемый кистью

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX

Определяет, как кисть горизонтально плитки тех областях, которые расширяются мимо его bitmap

```cpp
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>Параметры

*extendModeX*<br/>
Значение, которое определяет, как кисть горизонтально плитки тех областях, которые простираются мимо его bitmap

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY

Определяет, как кисть вертикально плитки тех областях, которые расширяются мимо его bitmap

```cpp
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>Параметры

*extendModeY*<br/>
Значение, которое определяет, как кисть вертикально плитки тех областях, которые простираются мимо его bitmap

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode

Определяет режим интерполяции, используемый при масштабировании или повороте кисти

```cpp
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>Параметры

*интерполяцияMode*<br/>
Режим интерполяции, используемый при масштабировании или повороте кисти

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
