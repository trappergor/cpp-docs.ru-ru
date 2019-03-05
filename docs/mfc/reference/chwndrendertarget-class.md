---
title: Класс CHwndRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: bf446cdf1ea064943ff92d66ac89b0e4177e6910
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270336"
---
# <a name="chwndrendertarget-class"></a>Класс CHwndRenderTarget

Оболочка для ID2D1HwndRenderTarget.

## <a name="syntax"></a>Синтаксис

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Создает объект CHwndRenderTarget из HWND.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHwndRenderTarget::Attach](#attach)|Присоединение существующих отрисовки целевой интерфейс к объекту|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Указывает, является ли перекрыто HWND, связанный с этой целевой объект отрисовки.|
|[CHwndRenderTarget::Create](#create)|Создает целевой объект отрисовки, связанный с окном|
|[CHwndRenderTarget::Detach](#detach)|Отсоединяет интерфейс целевой объект отрисовки из объекта|
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Возвращает HWND, связанный с данным объектом рендеринга.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Возвращает интерфейс ID2D1HwndRenderTarget.|
|[CHwndRenderTarget::ReCreate](#recreate)|Повторно создает целевой объект отрисовки, связанный с окном|
|[CHwndRenderTarget::Resize](#resize)|Изменяет размер целевого объекта отрисовки по размеру указанного пикселя|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Возвращает интерфейс ID2D1HwndRenderTarget.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Указатель на объект ID2D1HwndRenderTarget.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="attach"></a>  CHwndRenderTarget::Attach

Присоединение существующих отрисовки целевой интерфейс к объекту

```
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Существующий интерфейс целевой объект отрисовки. Не может иметь значение NULL

##  <a name="checkwindowstate"></a>  CHwndRenderTarget::CheckWindowState

Указывает, является ли перекрыто HWND, связанный с этой целевой объект отрисовки.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее ли целевой объект отрисовки HWND, связанный с данным перекрыто.

##  <a name="chwndrendertarget"></a>  CHwndRenderTarget::CHwndRenderTarget

Создает объект CHwndRenderTarget из HWND.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Параметры

*hwnd*<br/>
Целевой объект отрисовки HWND, связанный с данным

##  <a name="create"></a>  CHwndRenderTarget::Create

Создает целевой объект отрисовки, связанный с окном

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Целевой объект отрисовки HWND, связанный с данным

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE

##  <a name="detach"></a>  CHwndRenderTarget::Detach

Отсоединяет интерфейс целевой объект отрисовки из объекта

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отсоединенной отображения интерфейса целевой объект.

##  <a name="gethwnd"></a>  CHwndRenderTarget::GetHwnd

Возвращает HWND, связанный с данным объектом рендеринга.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целевой объект отрисовки HWND, связанный с данным.

##  <a name="gethwndrendertarget"></a>  CHwndRenderTarget::GetHwndRenderTarget

Возвращает интерфейс ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.

##  <a name="m_phwndrendertarget"></a>  CHwndRenderTarget::m_pHwndRenderTarget

Указатель на объект ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

##  <a name="operator_id2d1hwndrendertarget_star"></a>  CHwndRenderTarget::operator ID2D1HwndRenderTarget *

Возвращает интерфейс ID2D1HwndRenderTarget.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.

##  <a name="recreate"></a>  CHwndRenderTarget::ReCreate

Повторно создает целевой объект отрисовки, связанный с окном

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Целевой объект отрисовки HWND, связанный с данным

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="resize"></a>  CHwndRenderTarget::Resize

Изменяет размер целевого объекта отрисовки по размеру указанного пикселя

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Новый размер целевого объекта отрисовки в пикселях устройства

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
