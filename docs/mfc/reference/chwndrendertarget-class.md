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
ms.openlocfilehash: d1669d89183cd971e1afe0f05a1bad040f6b07df
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752705"
---
# <a name="chwndrendertarget-class"></a>Класс CHwndRenderTarget

Обертка для ID2D1HwndRenderTarget.

## <a name="syntax"></a>Синтаксис

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Строит объект CHwndRenderTarget из HWND.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHwndRenderTarget:Attach](#attach)|Прикрепляет существующий целевой интерфейс рендера к объекту|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Указывает, является ли HWND, связанный с этой целью рендеринга, окклюзией.|
|[CHwndRenderTarget::Создание](#create)|Создает цель рендеринга, связанная с окном|
|[CHwndRenderTarget::Detach](#detach)|Отеки визуализировать целевой интерфейс от объекта|
|[CHwndRenderTarget:GetHwnd](#gethwnd)|Возвращает HWND, связанный с этой целью рендеринга.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Возвращает интерфейс ID2D1HwndRenderTarget.|
|[CHwndRenderTarget::ReCreate](#recreate)|Повторное создание цели рендера, связанной с окном|
|[CHwndRenderTarget::Resize](#resize)|Изменяет размер цели рендера на указанный размер пикселя|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CHwndRenderTarget:оператор ID2D1HwndRenderTarget](#operator_id2d1hwndrendertarget_star)|Возвращает интерфейс ID2D1HwndRenderTarget.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Указатель на объект ID2D1HwndRenderTarget.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget:Attach

Прикрепляет существующий целевой интерфейс рендера к объекту

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Существующий целевой интерфейс рендеринга. Не может быть NULL

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState

Указывает, является ли HWND, связанный с этой целью рендеринга, окклюзией.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывавкоторое на то, является ли HWND, связанный с этой целью рендеринга, окклюзией.

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget

Строит объект CHwndRenderTarget из HWND.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
HWND, связанный с этой целью рендеринга

## <a name="chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::Создание

Создает цель рендеринга, связанная с окном

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
HWND, связанный с этой целью рендеринга

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE

## <a name="chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderTarget::Detach

Отеки визуализировать целевой интерфейс от объекта

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс рендеринга.

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderTarget:GetHwnd

Возвращает HWND, связанный с этой целью рендеринга.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

HWND, связанный с этой целью рендеринга.

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget

Возвращает интерфейс ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1HwndRenderTarget или NULL, если объект еще не инициализирован.

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget

Указатель на объект ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget:оператор ID2D1HwndRenderTarget

Возвращает интерфейс ID2D1HwndRenderTarget.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1HwndRenderTarget или NULL, если объект еще не инициализирован.

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndRenderTarget::ReCreate

Повторное создание цели рендера, связанной с окном

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
HWND, связанный с этой целью рендеринга

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::Resize

Изменяет размер цели рендера на указанный размер пикселя

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Новый размер цели рендеринга в пикселях устройства

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
