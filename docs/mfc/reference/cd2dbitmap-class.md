---
title: Класс CD2DBitmap
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: a3cabb00ded7dbc5f9c396a1de767058443a4436
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754209"
---
# <a name="cd2dbitmap-class"></a>Класс CD2DBitmap

Обертка для ID2D1Bitmap.

## <a name="syntax"></a>Синтаксис

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Перегружен. Строит объект CD2DBitmap от HBITMAP.|
|[CD2DBitmap:: »CD2DBitmap](#_dtorcd2dbitmap)|Деструктор Вызывается при уничтожении объекта битной карты D2D.|

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Перегружен. Строит объект CD2DBitmap.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap:Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DBitmap:CopyFromBitmap](#copyfrombitmap)|Копирует указанный регион из указанной битной карты в текущую битную карту|
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Копирует указанный регион из памяти в текущую битную карту|
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Копирует указанный регион из указанной цели рендеринга в текущую битную карту|
|[CD2DBitmap::Создание](#create)|Создает CD2DBitmap. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmap::Destroy](#destroy)|Уничтожает объект CD2DBitmap. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBitmap::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DBitmap::Get](#get)|Возвращает интерфейс ID2D1Bitmap|
|[CD2DBitmap::GetDPI](#getdpi)|Вернуть точки на дюйм (DPI) бит-карты|
|[CD2DBitmap:GetPixelFormat](#getpixelformat)|Извлекает формат пикселя и альфа-режим битной карты|
|[CD2DBitmap:GetPixelSize](#getpixelsize)|Возвращает размер в зависимых от устройства единиц (пикселей) битовой карты|
|[CD2DBitmap:GetSize](#getsize)|Возвращает размер, в устройстве-независимых пикселей (DIPs), бит-карты|
|[CD2DBitmap::IsValid](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap::CommonInit](#commoninit)|Инициализация объекта|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap:оператор ID2D1Bitmap](#operator_id2d1bitmap_star)|Возвращает интерфейс ID2D1Bitmap|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|ПРАВДА, если m_hBmpSrc должны быть уничтожены; в противном случае FALSE.|
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Ручка исходной карты.|
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Тип ресурса.|
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|Хранит указатель на объект ID2D1Bitmap.|
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Размер назначения Bitmap.|
|[CD2DBitmap::m_strPath](#m_strpath)|Путь файла Botmap.|
|[CD2DBitmap::m_uiResID](#m_uiresid)|Идентификатор ресурса Bitmap.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2DBitmap:: »CD2DBitmap

Деструктор Вызывается при уничтожении объекта битной карты D2D.

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a>CD2DBitmap:Attach

Прикрепляет существующий интерфейс ресурса к объекту.

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL.

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2DBitmap::CD2DBitmap

Строит объект CD2DBitmap из ресурса.

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*uiResID*<br/>
Идентификационный номер ресурса.

*lpszType*<br/>
Указатель на нулевую строку, содержащую тип ресурса.

*размерDest*<br/>
Размер назначения битной карты.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

*lpszPath*<br/>
Указатель на нулевую строку, содержащую имя файла.

*hbmpSrc*<br/>
Ручка к бит-карте.

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2DBitmap::CommonInit

Инициализирует объект.

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>CD2DBitmap:CopyFromBitmap

Копирует указанный регион из указанной битовой карты в текущую битную карту.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Биткарта для копирования.

*destPoint*<br/>
В текущей биткарте скопирован верхний левый угол области, в которую указывает область srcRect.

*srcRect*<br/>
Область бит-карты для копирования.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>CD2DBitmap::CopyFromMemory

Копирует указанный регион из памяти в текущую битную карту.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>Параметры

*srcData*<br/>
Копируемые данные.

*Шаг*<br/>
Шаг, или шаг, исходной битной карты, хранящейся в srcData. Шаг — это количество байт сканлина (один ряд пикселей в памяти). Шаг можно вычислить по следующей \* формуле: ширина пикселя байтами на пиксель и обивка памяти.

*destRect*<br/>
В текущей биткарте скопирован верхний левый угол области, в которую указывает область srcRect.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>CD2DBitmap::CopyFromRenderTarget

Копирует указанный регион из указанной цели влирении в текущую битную карту.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Цель рендеринга, содержащая область для копирования.

*destPoint*<br/>
В текущей биткарте скопирован верхний левый угол области, в которую указывает область srcRect.

*srcRect*<br/>
Область renderTarget для копирования.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dbitmapcreate"></a><a name="create"></a>CD2DBitmap::Создание

Создает CD2DBitmap.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a>CD2DBitmap::Destroy

Уничтожает объект CD2DBitmap.

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a>CD2DBitmap::Detach

Отсоединяет интерфейс ресурса с объекта.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dbitmapget"></a><a name="get"></a>CD2DBitmap::Get

Возвращает интерфейс ID2D1Bitmap.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Bitmap или NULL, если объект еще не инициализирован.

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2DBitmap::GetDPI

Верните точки на дюйм (DPI) битной карты.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальный и вертикальный DPI битной карты.

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2DBitmap:GetPixelFormat

Извлекает формат пикселя и альфа-режим битной карты

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Возвращаемое значение

Формат пикселей и альфа-режим битной карты.

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>CD2DBitmap:GetPixelSize

Возвращает размер, в устройстве-зависимых единицах (пикселей), битной карты.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер, в пикселях, бит-карты.

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a>CD2DBitmap:GetSize

Возвращает размер в независящих от устройств пикселей (DIPs) битовой карты.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер, в DIPs, бит-карты.

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2DBitmap::IsValid

Проверка достоверности ресурса.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2DBitmap::m_bAutoDestroyHBMP

ПРАВДА, если m_hBmpSrc должны быть уничтожены; в противном случае FALSE.

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a>CD2DBitmap::m_hBmpSrc

Ручка исходной карты.

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a>CD2DBitmap::m_lpszType

Тип ресурса.

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a>CD2DBitmap::m_pBitmap

Хранит указатель на объект ID2D1Bitmap.

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a>CD2DBitmap::m_sizeDest

Размер назначения Bitmap.

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a>CD2DBitmap::m_strPath

Путь файла Botmap.

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a>CD2DBitmap::m_uiResID

Идентификатор ресурса Bitmap.

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2DBitmap:оператор ID2D1Bitmap

Возвращает интерфейс ID2D1Bitmap

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Bitmap или NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
