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
ms.openlocfilehash: 8ba8c8819b47185315d67d732fc90ab2ffc0ad0a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752935"
---
# <a name="cbitmaprendertarget-class"></a>Класс CBitmapRenderTarget

Обертка для ID2D1BitmapRenderTarget.

## <a name="syntax"></a>Синтаксис

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Строит объект CBitmapRenderTarget.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::Attach](#attach)|Прикрепляет существующий целевой интерфейс рендера к объекту|
|[CBitmapRenderTarget::Detach](#detach)|Отеки визуализировать целевой интерфейс от объекта|
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Извлекает битную карту для этой цели рендеринга. Возвращается бит-карта может быть использована для операций рисования.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Возвращает интерфейс ID2D1BitmapRenderTarget|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget:оператор ID2D1BitmapRenderTarget](#operator_id2d1bitmaprendertarget_star)|Возвращает интерфейс ID2D1BitmapRenderTarget|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Указатель на объект ID2D1BitmapRenderTarget.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a>CBitmapRenderTarget::Attach

Прикрепляет существующий целевой интерфейс рендера к объекту

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Существующий целевой интерфейс рендеринга. Не может быть NULL

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget

Строит объект CBitmapRenderTarget.

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a>CBitmapRenderTarget::Detach

Отеки визуализировать целевой интерфейс от объекта

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс рендеринга.

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap

Извлекает битную карту для этой цели рендеринга. Возвращается бит-карта может быть использована для операций рисования.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Параметры

*Растрового изображения*<br/>
Когда этот метод возвращается, содержит действительную битовую карту для этой цели рендеринга. Эта бит-карта может быть использована для операций рисования.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget

Возвращает интерфейс ID2D1BitmapRenderTarget

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapRenderTarget или NULL, если объект еще не инициализирован.

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a>CBitmapRenderTarget::m_pBitmapRenderTarget

Указатель на объект ID2D1BitmapRenderTarget.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget:оператор ID2D1BitmapRenderTarget

Возвращает интерфейс ID2D1BitmapRenderTarget

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1BitmapRenderTarget или NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
