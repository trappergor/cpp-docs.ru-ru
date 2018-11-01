---
title: Класс CBitmapRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: ffead8d1f4a903fba79e4b22eefbf0a2955f56fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562244"
---
# <a name="cbitmaprendertarget-class"></a>Класс CBitmapRenderTarget

Оболочка для ID2D1BitmapRenderTarget.

## <a name="syntax"></a>Синтаксис

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Создает объект CBitmapRenderTarget.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::Attach](#attach)|Присоединение существующих отрисовки целевой интерфейс к объекту|
|[CBitmapRenderTarget::Detach](#detach)|Отсоединяет интерфейс целевой объект отрисовки из объекта|
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Извлекает растрового изображения для этого целевого объекта отрисовки. Возвращаемый точечный рисунок можно использовать для операций рисования.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Возвращает интерфейс ID2D1BitmapRenderTarget|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Возвращает интерфейс ID2D1BitmapRenderTarget|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Указатель на объект ID2D1BitmapRenderTarget.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="attach"></a>  CBitmapRenderTarget::Attach

Присоединение существующих отрисовки целевой интерфейс к объекту

```
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Существующий интерфейс целевой объект отрисовки. Не может иметь значение NULL

##  <a name="cbitmaprendertarget"></a>  CBitmapRenderTarget::CBitmapRenderTarget

Создает объект CBitmapRenderTarget.

```
CBitmapRenderTarget();
```

##  <a name="detach"></a>  CBitmapRenderTarget::Detach

Отсоединяет интерфейс целевой объект отрисовки из объекта

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отсоединенной отображения интерфейса целевой объект.

##  <a name="getbitmap"></a>  CBitmapRenderTarget::GetBitmap

Извлекает растрового изображения для этого целевого объекта отрисовки. Возвращаемый точечный рисунок можно использовать для операций рисования.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Параметры

*Точечный рисунок*<br/>
При возвращении данного метода содержит недопустимый точечный рисунок для этого целевого объекта отрисовки. Этот рисунок может использоваться для операции рисования.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="getbitmaprendertarget"></a>  CBitmapRenderTarget::GetBitmapRenderTarget

Возвращает интерфейс ID2D1BitmapRenderTarget

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.

##  <a name="m_pbitmaprendertarget"></a>  CBitmapRenderTarget::m_pBitmapRenderTarget

Указатель на объект ID2D1BitmapRenderTarget.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

##  <a name="operator_id2d1bitmaprendertarget_star"></a>  CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *

Возвращает интерфейс ID2D1BitmapRenderTarget

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
